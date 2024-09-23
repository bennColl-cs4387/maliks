
# Investigation Log

### Looking at evidence at gtpd branch

```bash
git checkout gtpd-archive
```

### Shows log of commits

```bash
git log --graph --pretty=format:"%C(red)%h%x09%Creset%C(blue)%C(bold)%ad%Creset %C(red)%cn%Creset  %C(green)%Creset %s" --date=iso
```

### Step 3: Only Entry by Logan That Day

```bash
git show a1c3e4b52f9d7f45ec7817b48997f865b372a0af
```

```
commit a1c3e4b52f9d7f45ec7817b48997f865b372a0af
Author: Logan Steinfield <lsteinfield@cityrecords.commit.gov>
Date:   Thu Mar 10 14:30:00 2020 +0000

    Investigation file #702315
    
    The incident took place two weeks ago, on March 2nd. Forensics report estimates the time to be between 13:20 and 16:45.
    
    A witness reported that nobody used the main gate during this time. The only entry point left was the side gate, which requires an RFID card for access.
    
    I collaborated with IT to extract key entries from the system logs for secured facilities on the site. The logs are stored on my personal branch 'detectives/lsteinfield'. The software lacks a search feature, so I'll manually look through it to see who accessed "SIDEGATE_890". The relevant log is placed in the evidence folder.
```

### Step 4: Investigating Harper

```bash
git checkout detectives/lsteinfield
git log -p -S'SIDEGATE_890'
```

Relevant Entries:

```
Author: Brock Stuickard stuickard.brock@commitfactory.com
Date: Sun Jul 14 15:23:00 2019 +0000
Message: ACCESS LOG COMMIT 15:23

Author: Cosmo Siwkonk siwkonk.cosmo@commitfactory.com
Date: Sun Jul 14 14:16:00 2019 +0000
Message: ACCESS LOG COMMIT 14:16

Author: Eddie Krowler <ekrowler@commitfactory.com>
Date: Mon Mar 2 09:20:00 2020 +0000
Message: ACCESS LOG COMMIT 09:20
```

### Step 5: Checking Harper's Address

```bash
git tag
git checkout street/baker_street
git log --grep="128 Baker Street"
```

```bash
git show c8411c73e49372dbdb644beef2ea841b403fc476
```

Cosmo wasn't there, but I found a green Hyundai.

### Step 6: Checking Other Suspects

```bash
git checkout street/elm_road
git log --grep="47 Elm Road"
```

Morgan was seen in the area. There was also a blue Toyota. Checking the solution.

### Step 7: Now checking beaconside

git checkout street/beaconside

Result: Case closed!
```bash

echo "Cosmo Siwkonk" | git hash-object --stdin | grep -iq -f /dev/stdin <(git show solution) && echo 'You found the murderer!' || echo 'No cigar, chief... Try again.'
```
