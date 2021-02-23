# ansible-101
Ansible 101

https://www.ansible.com/hubfs//AnsibleFest%20ATL%20Slide%20Decks/Running%20Ansible%20at%20Scale%20-%20AnsibleFest%202019.pdf

# Basic setup

1. hosts file
2. role
3. playbook file
4. run command `ansible-playbook -i hosts localhost.yml --ask-become-pass`

# Ansible modules

1. create & update file using modules  https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html 
2. homebrew modules (htop) https://docs.ansible.com/ansible/latest/collections/community/general/homebrew_module.html
3. osx defaults module: https://docs.ansible.com/ansible/latest/collections/community/general/osx_defaults_module.html

```
~ % defaults read /Library/./Preferences/com.apple.SoftwareUpdate.plist
{
    AutomaticCheckEnabled = YES;
    AutomaticDownload = 1;
    AutomaticallyInstallMacOSUpdates = 0;
    ConfigDataInstall = 0;
    CriticalUpdateInstall = 0;
    LastAttemptBuildVersion = "10.15.7 (19H114)";
    LastAttemptSystemVersion = "10.15.7 (19H114)";
    LastBackgroundSuccessfulDate = "2021-02-23 07:52:50 +0000";
    LastFullSuccessfulDate = "2021-02-23 07:52:51 +0000";
    LastRecommendedMajorOSBundleIdentifier = "com.apple.InstallAssistant.macOSBigSur";
    LastRecommendedUpdatesAvailable = 3;
    LastResultCode = 0;
    LastSessionSuccessful = 1;
    LastSuccessfulDate = "2021-02-23 07:52:51 +0000";
    LastUpdatesAvailable = 3;
    PrimaryLanguages =     (
        "en-LT",
        "en-GB"
    );
    RecommendedUpdates =     (
                {
            "Display Name" = Safari;
            "Display Version" = "14.0.3";
            Identifier = "Safari14.0.3CatalinaAuto";
            "Product Key" = "071-03270";
        },
                {
            "Display Name" = "macOS Catalina 10.15.7 Supplemental Update";
            "Display Version" = "10.15.7";
            Identifier = "macOS Catalina 10.15.7 Supplemental Update";
            "Product Key" = "071-05425";
        },
                {
            "Display Name" = "macOS Catalina Security Update 2021-001";
            "Display Version" = "10.15.7";
            Identifier = "macOS Catalina Security Update 2021-001";
            "Product Key" = "001-93719";
        }
    );
}
```
```
% defaults read /Library/./Preferences/com.apple.SoftwareUpdate.plist | grep AutomaticCheckEnabled
    AutomaticCheckEnabled = True;
% defaults read /Library/./Preferences/com.apple.SoftwareUpdate.plist | grep AutomaticCheckEnabled
    AutomaticCheckEnabled = False;
```