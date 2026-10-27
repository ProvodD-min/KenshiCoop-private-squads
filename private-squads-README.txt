KenshiCoop private squads and separate wallets; experimental two-player protocol 56
Base: https://github.com/nhoral/KenshiCoop commit 5a761e19a4184b42315e96ea7e92e3c1403d54db, AGPLv3.
DLL SHA256: 26b784b64476cb6655b276f26e4e062dd0e2b98f0f2e247a05d65132809d34b0

Read Свои-отряды.md for setup and exact limits. Both peers require this DLL.
Set KENSHICOOP_PRIVATE_SQUADS=1 and KENSHICOOP_SEPARATE_MONEY=1 on both peers.
Preserve coop_squads.dat and coop_wallets.dat inside coordinated saves.

Build: VC2010 SP1 x64 16.00.40219.01 /O2 /GL /MD /LTCG, SDK7.1, Boost1.60,
official KenshiLib headers and Ogre/MyGUI SDK libraries, patched ENet1.3.18.
Whole-program optimization is required for the actual import thunk path.
The included portable build recipe expects work/KenshiCoop, work/KenshiLib,
work/coop-anything/local/build-tools, local/test-host/KenshiLib.dll.
Generate import library from all10131 named KenshiLib exports; pefile max_symbol_exports=65536.
Compiler, game binaries and runtime libraries are not redistributed.

Native tests: scripts/test_private_recruit.cpp (no arguments) and
scripts/test_private_squad_session.cpp (one NEW test directory argument).
Compile with VC10 x64 /EHsc /D_CRT_SECURE_NO_WARNINGS. Session tests use real
Win32 file IO only in that fresh test directory. No game process needed.
