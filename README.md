# BookFiler Desktop
A desktop tool by Bookfiler™ for managing local machine files. Bookfiler is designed for personal and business organization.

In our busy work schedule, files are often downloaded and left on the desktop or download folder indefintely. Over time files are often lost. Bookfiler™ Desktop offers machine learning and artificial intelligence solutions for organizing your files locally on your computer. Bookfiler™ Desktop does not require an internet connection, guarenteeing that it won't leak your personal financial information to the internet.

# File Naming System
| Tiers | Example |
| :-- | :-- |
| Primary Entity | `MyBusiness` |
| Lateral Category | `MyBusiness_media` containing `MyBusiness_images` |
| Category | `MyBusiness_images` |
| Lateral Sub Category | `MyBusiness_images_marketing` containing `MyBusiness_images_brochure` |
| Sub Category | `MyBusiness_images_brochure` |

## What are lateral tiers?
Often a large project wants to stay under one top folder to be contained for easy file sync with remote servers; however, media components will often take up the most hard drive space and will take too long to be synced with remote servers. Lateral tiers are part of the primary entity, but are placed outide in a lateral directory so the files are not synced.

# Version Control System
Git is used for version control. Since Git has a strong copyleft license, it must be installed separately.

## See history for file
```shell
git log -p <file name>
```

## cloning into an exsting directory
https://stackoverflow.com/questions/5377960/whats-the-best-practice-to-git-clone-into-an-existing-folder

# Document Identification Utility
Uses an intelligent reader to identify a file and tag the file name. For example:

| Original Document Name | Document Content | New Document Name |
| :-- | :-- | :-- |
| `2019invbusdoc.pdf` | Invoice to MyBusiness due 5/6/2019 | `MyBusiness_invoice-in_D20190506.pdf` |

## Document Identification Utility requires:
* Hierarchy context
* Machine learning file

## Software Steps:
1. Convert document to a hOCR file
2. Use machine learning and hierarchy context to identify
3. Save identification information into local client history

## Why do file names become so long?
File names become longer to become more human readable. The Document Filing Utility will be able to read these names to properly file them. Original names and meta data are stored by the Document Identification Utility.

Long file names mean that file may be separated and transmitted through email or online with context of the hierarchy. 

# Hierarchy Context
The hierarchy information combined between all active primary entities added into the desktop client. Each primary entity has hierarchy information stored in the top level folder.

    .
    ├── .git                    # git repository for the primary entity lateral category
    ├── .bookfiler              # Bookfiler™ meta data about the primary entity
    │   ├── hierarchy.dat       # SQLITE database file with hierarchy data
    │   ├── ...
    │   └── ...
    └── ...
    
The hierarchy context can be visually described as:

    .
    ├── primaryEntity1          # Bookfiler™ meta data for primary entity 1
    │   └── hierarchy.dat       # SQLITE database file with hierarchy data
    ├── primaryEntity2          # Bookfiler™ meta data for primary entity 2
    │   └── hierarchy.dat       # SQLITE database file with hierarchy data
    └── ...

## Previous Version
In previous versions the hierarchy data was known as the "Logic"

| Hierarchy System | Logic System |
| :-- | :-- |
| Primary Entity  | A |
| Category | B |
| Sub Category | C |

The concept was similar, but has now been renamed to a hierarchy system.

## Organize documents by type or by case?
Organize by type example: An invoice being placed in a folder with other invoices. May further by organized by date. This organization may be better for end of year taxes.

Organize by case example: An invoice is placed in a folder for a client project. This may be easier for gathering related invoices for reimbursement or collections. 

In the plain filesystem only one may be chosen unless the file is duplicated. Duplications make version control more difficult. Bookfiler™ organizes by type in the filesystem, then creates virtual links to cases.

# Quickbook compatability
QuickBooks for Windows
Common QuickBooks files
|File extension|File type|Description|
|:--|:--|:--|
|QBW|QuickBooks Company file|When you create a company file, QuickBooks creates a file with a .qbw extension. This file holds your company file and account info. For example, if you create a company called MyBusiness, QuickBooks saves the company file as: MyBusiness.qbw.|
|QBB|QuickBooks Backup file|When you back up your company file, QuickBooks creates a backup file with a .qbb extension. Here's how to back up your company file> and how to restore your company file from a backup.|
|QBM|QuickBooks Portable file|When you e-mail or move a company file, QuickBooks creates a compressed version of your company file with a .qbm extension.
For example, if you create a portable company file for MyBusiness, QuickBooks saves it as: MyBusiness.qbm.|
|QBO|QuickBooks Bank Statement file|When you download transactions from your bank, QuickBooks opens them from a file with a .qbo extension.You can import a QBO file to quickly get transactions into your bank register.|

Source: https://quickbooks.intuit.com/learn-support/en-us/import-or-export-data-files/file-types-and-extensions-used-by-quickbooks-desktop/00/203775
