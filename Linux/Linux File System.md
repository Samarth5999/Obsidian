The original filesystem introduced with the Linux is called the **Extended filesystem** (ext). Ext uses virtual directories to handle physical devices and storing data in fixed-length blocks on the physical devices.

The ext filesystem uses inodes to track information about the files stored in the virtual directory.

### Inodes

The inode system creates a separate table on each physical device, called the inode table, to store file information. Each stored file in the virtual directory has an entry in the inode table.

The extended part of the name comes from the additional data that it tracks on each file, which consists of:
• The filename
• File Size (upto 2 GB in ext & upto 3 TB to 32 TB in `ext2`)
• The owner of the file & the group the file belongs to
• Access permissions for the file
• Pointers to each disk block that contains data from the file

Each file has one inode, and can have multiple names (link), all names map onto its single inode

An inode does not store the actual file content directly. Instead, it contains pointers to the blocks on disk where the file’s data is stored.

#### Structure of an inode

A typical inode contains:

1. Metadata: File type, permissions, owner, timestamps, size, link count

2. Pointers to data blocks: Linux (and UNIX-like filesystems) usually use a combination of:

* Direct pointers → point straight to data blocks
* Single indirect pointer → points to a block that contains addresses of data blocks
* Double indirect pointer → points to a block that points to blocks containing data addresses
* Triple indirect pointer → for very large files

```ad-example
Suppose a file is 10 KB and each disk block is 4 KB:
- The inode has 12 direct pointers (most files fit here).
- Each direct pointer points to a 4 KB block → first 3 blocks = 12 KB of data.  
- If the file is bigger, the **single indirect pointer** is used → points to a block listing addresses of more data blocks.  
- For huge files, double or triple indirect pointers are used.
```


## Journaling Filesystems

It provides a new level of safety for linux filesystem. 
Instead of writing data directly to the storage device and then updating the inode table, journaling filesystems write file changes into a temporary file ( journal) first. After data is successfully written to the storage device and the inode table, the journal entry is deleted.

#### Journaling Modes

1. Data Mode: Both inode and file data journaled. Low risk of losing data, but poor performance.
2. Ordered Mode: Only inode data is written to the journal, but not removes until file data is successfully written. Good compromise between performance and safety.
3. Writeback Mode: Only inode data is written to the journal, no control over when the file data is written. Higher risk of losing data, but still better than not using journaling.



