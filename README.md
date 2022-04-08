# NtQuerySection-sample
Retrieve Memory mapped file size on windows with NtQuerySection and _SECTION_BASIC_INFORMATION

```
typedef struct _SECTION_BASIC_INFORMATION
{
    PVOID BaseAddress;
    ULONG AllocationAttributes;
    LARGE_INTEGER MaximumSize;
} SECTION_BASIC_INFORMATION, *PSECTION_BASIC_INFORMATION;
```

