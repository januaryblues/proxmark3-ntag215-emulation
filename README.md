# proxmark3-ntag215-emulation
A memory map for proxmark3 emulation of an iPhone compatible NDEF ready NTAG215 tag

# Usage instructions
The json files in this repo can be used with a Proxmark3 board to emulate an NTAG215 style tag, in a manner that is compatible with standard iPhone NFCCore sessions, so can be used with an iOS app. The memory of the tag has been bootstrapped such that it is 'NDEF ready' and can receive NDEF messages without any additional formatting.

The repo contains 2x different files. One has a lot of memory, which is super useful but can make the read/write from the iPhone a bit slow. The other has less memory (24 blocks), so is faster. Both files contain more memory than a standard 'real life' NTAG215 tag.

1. Start the Proxmark 3 client
2. Load the file into the emulator memory: `hf mfu eload -f /path/to/file.json`
3. Start the tag emulation: `hf 14a sim -t 2 -u 04FC63D29C3980`
4. Read/Write to the tag with an iPhone
