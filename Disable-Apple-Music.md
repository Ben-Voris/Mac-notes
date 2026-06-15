# Disabling Apple Music

Apple Music cannot be uninstalled, but a configuration profile can block it
from launching. One known trigger is connecting a Bluetooth audio device.

[Block Apple Music with a Profile](https://discussions.apple.com/thread/256082575?sortBy=rank)
explains the approach, which refers to
[Activating the profile](https://discussions.apple.com/docs/DOC-250009168)
(starts with camera, but covers `Apple Configurator` generally).

## Using the profile in this repo

A ready-made profile is in this repo: [`NoAppleMusic.mobileconfig`](NoAppleMusic.mobileconfig).

### Installing

1. Double-click `NoAppleMusic.mobileconfig`. A popup will appear prompting
   you to review the profile in System Settings.
2. Open `System Settings` &rarr; `General` &rarr; `Device Management`.
3. Double-click the profile listed there to review it.
4. Click `Install…`
5. Click `Install` on the confirmation prompt (`Are you sure you want to
   install profile "Block Apple Music"?`).
6. Click **Install** again on the second prompt showing the profile description,
   then enter your password when prompted.

The profile will show settings such as "Allow Apple Personalized Advertising."
These entries with `allow: true` do not change your existing preferences —
they mean the profile is not restricting those settings via MDM.

### Verifying installation

```shell
profiles list
```

You should see one user configuration profile. To see more detail:

```shell
profiles show
```

Look for `payload[1] type = com.apple.applicationaccess` and
`payload[1] name = Restrictions`.

## After a macOS upgrade

The profile may be listed but stop working. To remove it and reinstall:

1. Remove the profile from the command line:

   ```shell
   profiles remove -identifier Bens-MacBook-Pro.6ED83DA8-4E4F-486F-8E86-260D6C80E0D5
   ```

   If you get `CPProfileManager error -205`, the identifier is wrong. Run
   `profiles list` to find the correct value and substitute it above.

2. Reinstall from the file as described in [Installing](#installing).

## Notes

- The profile uses the key `blockedAppBundleIDs` (the current Apple MDM key).
  Older profiles may use the deprecated `blacklistedAppBundleIDs`, which may
  be ignored on newer macOS versions.
- Reports in the Apple Discussions thread indicate the profile approach does
  not work for everyone. If it fails, [noTunes](https://github.com/tombonez/noTunes)
  is a reliable alternative.
