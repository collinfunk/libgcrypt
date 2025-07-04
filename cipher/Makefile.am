# Makefile for cipher modules
# Copyright (C) 1998, 1999, 2000, 2001, 2002,
#               2003, 2009 Free Software Foundation, Inc.
#
# This file is part of Libgcrypt.
#
# Libgcrypt is free software; you can redistribute it and/or modify
# it under the terms of the GNU Lesser General Public License as
# published by the Free Software Foundation; either version 2.1 of
# the License, or (at your option) any later version.
#
# Libgcrypt is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public
# License along with this program; if not, see <http://www.gnu.org/licenses/>.

# Process this file with automake to produce Makefile.in

# Need to include ../src in addition to top_srcdir because gcrypt.h is
# a built header.
AM_CPPFLAGS = -I../src -I$(top_srcdir)/src -I../mpi -I$(top_srcdir)/mpi
AM_CFLAGS = $(GPG_ERROR_CFLAGS)

AM_CCASFLAGS = $(NOEXECSTACK_FLAGS)

EXTRA_DIST = gost-s-box.c kyber-common.c kyber-kdep.c \
             dilithium-common.c dilithium-dep.c

CLEANFILES = gost-s-box$(EXEEXT_FOR_BUILD)
DISTCLEANFILES = gost-sb.h

noinst_LTLIBRARIES = libcipher.la

GCRYPT_MODULES = @GCRYPT_CIPHERS@ @GCRYPT_PUBKEY_CIPHERS@ \
                 @GCRYPT_DIGESTS@ @GCRYPT_KDFS@

libcipher_la_DEPENDENCIES = $(GCRYPT_MODULES)
libcipher_la_LIBADD = $(GCRYPT_MODULES)

libcipher_la_SOURCES = \
	cipher.c cipher-internal.h \
	cipher-cbc.c \
	cipher-cfb.c \
	cipher-ofb.c \
	cipher-ctr.c \
	cipher-aeswrap.c \
	cipher-ccm.c \
	cipher-cmac.c \
	cipher-gcm.c \
	cipher-poly1305.c \
	cipher-ocb.c \
	cipher-xts.c \
	cipher-eax.c \
	cipher-siv.c \
	cipher-gcm-siv.c \
	pubkey.c pubkey-internal.h pubkey-util.c \
	md.c \
	mac.c mac-internal.h \
	mac-hmac.c mac-cmac.c mac-gmac.c mac-poly1305.c \
	poly1305.c poly1305-internal.h \
	kem.c sntrup761.c sntrup761.h kem-ecc.c kem-ecc.h \
	mceliece6688128f.c mceliece6688128f.h \
	kdf.c kdf-internal.h \
	bithelp.h  \
	bufhelp.h  \
	bulkhelp.h \
	primegen.c \
	hash-common.c hash-common.h \
	dsa-common.c rsa-common.c \
	sha1.h

EXTRA_libcipher_la_SOURCES = \
	asm-common-aarch64.h \
	asm-common-amd64.h \
	asm-common-i386.h \
	asm-common-s390x.h \
	asm-inline-s390x.h \
	asm-poly1305-aarch64.h \
	asm-poly1305-amd64.h \
	asm-poly1305-s390x.h \
	aria.c aria-aesni-avx-amd64.S aria-aesni-avx2-amd64.S \
	aria-gfni-avx512-amd64.S \
	arcfour.c arcfour-amd64.S \
	blowfish.c blowfish-amd64.S blowfish-arm.S \
	cast5.c cast5-amd64.S cast5-arm.S \
	chacha20.c chacha20-amd64-ssse3.S chacha20-amd64-avx2.S \
	chacha20-amd64-avx512.S chacha20-armv7-neon.S chacha20-aarch64.S \
	chacha20-ppc.c chacha20-s390x.S chacha20-p10le-8x.s \
	chacha20-riscv-v.c \
	cipher-gcm-ppc.c cipher-gcm-intel-pclmul.c \
	cipher-gcm-aarch64-simd.c cipher-gcm-armv7-neon.S \
	cipher-gcm-armv8-aarch32-ce.S cipher-gcm-armv8-aarch64-ce.S \
	cipher-gcm-riscv-zbb-zbc.c \
	crc.c crc-intel-pclmul.c crc-armv8-ce.c \
	crc-armv8-aarch64-ce.S \
	crc-ppc.c \
	des.c des-amd64.S \
	dilithium.c dilithium.h pubkey-dilithium.c \
	dsa.c \
	elgamal.c \
	ecc.c ecc-curves.c ecc-misc.c ecc-common.h \
	ecc-ecdh.c ecc-ecdsa.c ecc-eddsa.c ecc-gost.c ecc-sm2.c \
	kyber.c kyber.h \
	idea.c \
	gost28147.c gost.h \
	gostr3411-94.c \
	md4.c \
	md5.c \
	poly1305-s390x.S poly1305-amd64-avx512.S \
	poly1305-p10le.s \
	rijndael.c rijndael-internal.h rijndael-tables.h   \
	rijndael-aesni.c rijndael-padlock.c                \
	rijndael-amd64.S rijndael-arm.S                    \
	rijndael-ssse3-amd64.c rijndael-ssse3-amd64-asm.S  \
	rijndael-vaes.c rijndael-vaes-avx2-amd64.S         \
	rijndael-vaes-i386.c rijndael-vaes-avx2-i386.S     \
	rijndael-armv8-ce.c rijndael-armv8-aarch32-ce.S    \
	rijndael-armv8-aarch64-ce.S rijndael-aarch64.S     \
	rijndael-ppc.c rijndael-ppc9le.c                   \
	rijndael-p10le.c rijndael-gcm-p10le.s              \
	rijndael-ppc-common.h rijndael-ppc-functions.h     \
	rijndael-s390x.c                                   \
	rijndael-vp-aarch64.c rijndael-vp-riscv.c          \
	rijndael-vp-simd128.h                              \
	rmd160.c \
	rsa.c \
	salsa20.c salsa20-amd64.S salsa20-armv7-neon.S \
	scrypt.c \
	seed.c \
	serpent.c serpent-sse2-amd64.S serpent-avx2-amd64.S \
	serpent-avx512-x86.c serpent-armv7-neon.S \
	simd-common-aarch64.h simd-common-ppc.h simd-common-riscv.h \
	sm4.c sm4-aesni-avx-amd64.S sm4-aesni-avx2-amd64.S \
	sm4-gfni-avx2-amd64.S sm4-gfni-avx512-amd64.S \
	sm4-aarch64.S sm4-armv8-aarch64-ce.S sm4-armv9-aarch64-sve-ce.S \
	sm4-ppc.c \
	sha1.c sha1-ssse3-amd64.S sha1-avx-amd64.S sha1-avx-bmi2-amd64.S \
	sha1-avx2-bmi2-amd64.S sha1-armv7-neon.S sha1-armv8-aarch32-ce.S \
	sha1-armv8-aarch64-ce.S sha1-intel-shaext.c \
	sha256.c sha256-ssse3-amd64.S sha256-avx-amd64.S \
	sha256-avx2-bmi2-amd64.S \
	sha256-armv8-aarch32-ce.S sha256-armv8-aarch64-ce.S \
	sha256-intel-shaext.c sha256-ppc.c \
	sha512.c sha512-ssse3-amd64.S sha512-avx-amd64.S \
	sha512-avx2-bmi2-amd64.S sha512-avx512-amd64.S \
	sha512-armv7-neon.S sha512-armv8-aarch64-ce.S sha512-arm.S \
	sha512-ppc.c sha512-ssse3-i386.c \
	sm3.c sm3-avx-bmi2-amd64.S sm3-aarch64.S sm3-armv8-aarch64-ce.S \
	keccak.c keccak_permute_32.h keccak_permute_64.h \
	keccak-armv7-neon.S keccak-amd64-avx512.S \
	stribog.c \
	tiger.c \
	whirlpool.c whirlpool-sse2-amd64.S \
	twofish.c twofish-amd64.S twofish-arm.S twofish-aarch64.S \
	twofish-avx2-amd64.S \
	rfc2268.c \
	camellia.c camellia.h camellia-glue.c camellia-aesni-avx-amd64.S \
	camellia-aesni-avx2-amd64.h \
	camellia-gfni-avx2-amd64.S camellia-gfni-avx512-amd64.S \
	camellia-vaes-avx2-amd64.S camellia-aesni-avx2-amd64.S \
	camellia-arm.S camellia-aarch64.S camellia-aarch64-ce.c \
	camellia-simd128.h camellia-ppc8le.c camellia-ppc9le.c \
	blake2.c \
	blake2b-amd64-avx2.S blake2b-amd64-avx512.S \
	blake2s-amd64-avx.S blake2s-amd64-avx512.S

gost28147.lo: gost-sb.h
gost-sb.h: gost-s-box$(EXEEXT_FOR_BUILD)
	./gost-s-box$(EXEEXT_FOR_BUILD) $@

gost-s-box$(EXEEXT_FOR_BUILD): gost-s-box.c
	$(CC_FOR_BUILD) $(CFLAGS_FOR_BUILD) $(LDFLAGS_FOR_BUILD) \
	    $(CPPFLAGS_FOR_BUILD) -o $@ $(srcdir)/gost-s-box.c


if ENABLE_O_FLAG_MUNGING
o_flag_munging = sed -e 's/[[:blank:]]-O\([2-9sgz][2-9sgz]*\)/ -O1 /g' -e 's/[[:blank:]]-Ofast/ -O1 /g'
else
o_flag_munging = cat
endif


# We need to lower the optimization for this module.
tiger.o: $(srcdir)/tiger.c Makefile
	`echo $(COMPILE) -c $< | $(o_flag_munging) `

tiger.lo: $(srcdir)/tiger.c Makefile
	`echo $(LTCOMPILE) -c $< | $(o_flag_munging) `


# We need to disable instrumentation for these modules as they use cc as
# thin assembly front-end and do not tolerate in-between function calls
# inserted by compiler as those functions may clobber the XMM registers.
if ENABLE_INSTRUMENTATION_MUNGING
instrumentation_munging = sed \
	-e 's/-fsanitize[=,\-][=,a-z,A-Z,0-9,\,,\-]*//g' \
	-e 's/-fprofile[=,\-][=,a-z,A-Z,0-9,\,,\-]*//g' \
	-e 's/-fcoverage[=,\-][=,a-z,A-Z,0-9,\,,\-]*//g'
else
instrumentation_munging = cat
endif

rijndael-aesni.o: $(srcdir)/rijndael-aesni.c Makefile
	`echo $(COMPILE) -c $< | $(instrumentation_munging) `

rijndael-aesni.lo: $(srcdir)/rijndael-aesni.c Makefile
	`echo $(LTCOMPILE) -c $< | $(instrumentation_munging) `

rijndael-ssse3-amd64.o: $(srcdir)/rijndael-ssse3-amd64.c Makefile
	`echo $(COMPILE) -c $< | $(instrumentation_munging) `

rijndael-ssse3-amd64.lo: $(srcdir)/rijndael-ssse3-amd64.c Makefile
	`echo $(LTCOMPILE) -c $< | $(instrumentation_munging) `

cipher-gcm-intel-pclmul.o: $(srcdir)/cipher-gcm-intel-pclmul.c Makefile
	`echo $(COMPILE) -c $< | $(instrumentation_munging) `

cipher-gcm-intel-pclmul.lo: $(srcdir)/cipher-gcm-intel-pclmul.c Makefile
	`echo $(LTCOMPILE) -c $< | $(instrumentation_munging) `

sha1-intel-shaext.o: $(srcdir)/sha1-intel-shaext.c Makefile
	`echo $(COMPILE) -c $< | $(instrumentation_munging) `

sha1-intel-shaext.lo: $(srcdir)/sha1-intel-shaext.c Makefile
	`echo $(LTCOMPILE) -c $< | $(instrumentation_munging) `

sha256-intel-shaext.o: $(srcdir)/sha256-intel-shaext.c Makefile
	`echo $(COMPILE) -c $< | $(instrumentation_munging) `

sha256-intel-shaext.lo: $(srcdir)/sha256-intel-shaext.c Makefile
	`echo $(LTCOMPILE) -c $< | $(instrumentation_munging) `

sha256-ssse3-i386.o: $(srcdir)/sha256-ssse3-i386.c Makefile
	`echo $(COMPILE) -c $< | $(instrumentation_munging) `

sha256-ssse3-i386.lo: $(srcdir)/sha256-ssse3-i386.c Makefile
	`echo $(LTCOMPILE) -c $< | $(instrumentation_munging) `

crc-intel-pclmul.o: $(srcdir)/crc-intel-pclmul.c Makefile
	`echo $(COMPILE) -c $< | $(instrumentation_munging) `

crc-intel-pclmul.lo: $(srcdir)/crc-intel-pclmul.c Makefile
	`echo $(LTCOMPILE) -c $< | $(instrumentation_munging) `

if ENABLE_PPC_VCRYPTO_EXTRA_CFLAGS
ppc_vcrypto_cflags = -O2 -maltivec -mvsx -mcrypto
else
ppc_vcrypto_cflags =
endif

rijndael-ppc.o: $(srcdir)/rijndael-ppc.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

rijndael-ppc.lo: $(srcdir)/rijndael-ppc.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

rijndael-ppc9le.o: $(srcdir)/rijndael-ppc9le.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

rijndael-ppc9le.lo: $(srcdir)/rijndael-ppc9le.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

rijndael-p10le.o: $(srcdir)/rijndael-p10le.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

rijndael-p10le.lo: $(srcdir)/rijndael-p10le.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

sha256-ppc.o: $(srcdir)/sha256-ppc.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

sha256-ppc.lo: $(srcdir)/sha256-ppc.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

sha512-ppc.o: $(srcdir)/sha512-ppc.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

sha512-ppc.lo: $(srcdir)/sha512-ppc.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

chacha20-ppc.o: $(srcdir)/chacha20-ppc.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

chacha20-ppc.lo: $(srcdir)/chacha20-ppc.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

crc-ppc.o: $(srcdir)/crc-ppc.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

crc-ppc.lo: $(srcdir)/crc-ppc.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

cipher-gcm-ppc.o: $(srcdir)/cipher-gcm-ppc.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

cipher-gcm-ppc.lo: $(srcdir)/cipher-gcm-ppc.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

camellia-ppc8le.o: $(srcdir)/camellia-ppc8le.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

camellia-ppc8le.lo: $(srcdir)/camellia-ppc8le.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

camellia-ppc9le.o: $(srcdir)/camellia-ppc9le.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

camellia-ppc9le.lo: $(srcdir)/camellia-ppc9le.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

sm4-ppc.o: $(srcdir)/sm4-ppc.c Makefile
	`echo $(COMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

sm4-ppc.lo: $(srcdir)/sm4-ppc.c Makefile
	`echo $(LTCOMPILE) $(ppc_vcrypto_cflags) -c $< | $(instrumentation_munging) `

if ENABLE_AARCH64_NEON_INTRINSICS_EXTRA_CFLAGS
aarch64_crypto_cflags = -O2 -march=armv8-a+simd+crypto
aarch64_simd_cflags = -O2 -march=armv8-a+simd
else
aarch64_crypto_cflags =
aarch64_simd_cflags =
endif

camellia-aarch64-ce.o: $(srcdir)/camellia-aarch64-ce.c Makefile
	`echo $(COMPILE) $(aarch64_crypto_cflags) -c $< | $(instrumentation_munging) `

camellia-aarch64-ce.lo: $(srcdir)/camellia-aarch64-ce.c Makefile
	`echo $(LTCOMPILE) $(aarch64_crypto_cflags) -c $< | $(instrumentation_munging) `

cipher-gcm-aarch64-simd.o: $(srcdir)/cipher-gcm-aarch64-simd.c Makefile
	`echo $(COMPILE) $(aarch64_simd_cflags) -c $< | $(instrumentation_munging) `

cipher-gcm-aarch64-simd.lo: $(srcdir)/cipher-gcm-aarch64-simd.c Makefile
	`echo $(LTCOMPILE) $(aarch64_simd_cflags) -c $< | $(instrumentation_munging) `

rijndael-vp-aarch64.o: $(srcdir)/rijndael-vp-aarch64.c Makefile
	`echo $(COMPILE) $(aarch64_simd_cflags) -c $< | $(instrumentation_munging) `

rijndael-vp-aarch64.lo: $(srcdir)/rijndael-vp-aarch64.c Makefile
	`echo $(LTCOMPILE) $(aarch64_simd_cflags) -c $< | $(instrumentation_munging) `

if ENABLE_X86_AVX512_INTRINSICS_EXTRA_CFLAGS
avx512f_cflags = -mavx512f
else
avx512f_cflags =
endif

serpent-avx512-x86.o: $(srcdir)/serpent-avx512-x86.c Makefile
	`echo $(COMPILE) $(avx512f_cflags) -c $< | $(instrumentation_munging) `

serpent-avx512-x86.lo: $(srcdir)/serpent-avx512-x86.c Makefile
	`echo $(LTCOMPILE) $(avx512f_cflags) -c $< | $(instrumentation_munging) `

if ENABLE_RISCV_VECTOR_INTRINSICS_EXTRA_CFLAGS
# Note: -mstrict-align needed for GCC-14 bug (disable unaligned vector loads)
riscv_vector_cflags = -O2 -march=rv64imafdcv -mstrict-align
else
riscv_vector_cflags =
endif

chacha20-riscv-v.o: $(srcdir)/chacha20-riscv-v.c Makefile
	`echo $(COMPILE) $(riscv_vector_cflags) -c $< | $(instrumentation_munging) `

chacha20-riscv-v.lo: $(srcdir)/chacha20-riscv-v.c Makefile
	`echo $(LTCOMPILE) $(riscv_vector_cflags) -c $< | $(instrumentation_munging) `

rijndael-vp-riscv.o: $(srcdir)/rijndael-vp-riscv.c Makefile
	`echo $(COMPILE) $(riscv_vector_cflags) -c $< | $(instrumentation_munging) `

rijndael-vp-riscv.lo: $(srcdir)/rijndael-vp-riscv.c Makefile
	`echo $(LTCOMPILE) $(riscv_vector_cflags) -c $< | $(instrumentation_munging) `
