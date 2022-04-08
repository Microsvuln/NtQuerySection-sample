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

```
if (HANDLE hMap = OpenFileMappingW(SECTION_QUERY|SECTION_MAP_READ, FALSE, name))
{
    SECTION_BASIC_INFORMATION sbi;
    if (0 <= ZwQuerySection(hMap, SectionBasicInformation, &sbi, sizeof(sbi), 0))
    {
        DbgPrint("section size = %I64x\n", sbi.Size.QuadPart);
    }
    CloseHandle(hMap);
}
```

Structure information :

https://processhacker.sourceforge.io/doc/ntmmapi_8h_source.html#l00178
