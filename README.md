# NtQuerySection-sample
Retrieve Memory mapped file size on windows with NtQuerySection and _SECTION_BASIC_INFORMATION

Required Structure :

```
typedef struct _SECTION_BASIC_INFORMATION
{
    PVOID BaseAddress;
    ULONG AllocationAttributes;
    LARGE_INTEGER MaximumSize;
} SECTION_BASIC_INFORMATION, *PSECTION_BASIC_INFORMATION;
```


The rest of the code :

` OpenFileMapping(SECTION_QUERY|FILE_MAP_READ|FILE_MAP_WRITE, FALSE, strSharedMemName); `
