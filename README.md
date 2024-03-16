# tryHackMe-crackthehash
 Repo for Crack The Hash challenge on tryhackme
 For cracking hashes, we can use hashcat. Works on windows or linux.

 hashcat -m 0 -a 0 {name}.txt rockyou.txt
 -> use -a 0 for dictionary mode attack
 -> use -m for slection of hash mode. leave empty for autodetect

 hash1 : easy (md5)
 hash2 : password123 (sha1)
 hash3 : letmein (sha2-256)

 for hash4, there was some difficulty using dictionary as blowfish hash was slow. Tred to do mask attack instead
 -> use -a 3 for mask mode attack
 -> use -m 3200 for blowfish
 -> use 01 ?l?u?d ?1?1?1?1 based on "https://security.stackexchange.com/questions/201931/hashcat-specify-number-of-characters"

 Final command:
 hashcat -m 3200 "C:\Users\xx\Documents\tryhackme\tryHackMe-crackthehash\hash4.txt" "C:\Users\xx\Documents\tryhackme\tryHackMe-crackthehash\rockyou.txt" -a 3 -1 ?l?u?d ?1?1?1?1

 jk. didnt work either

 instead, used flag -w 3 for command for faster crack, as blowfish takes suuuuper long (took abt 10+mins)

 hash4 : bleh (blowfish)
 
 hash 5 md4 decrypt didnt work on my rockyou.txt, turns out it must be Eternty22 and not eternity22 (My version of rockyou has only eternity22)

 hash5 : Eternity22 (md4)

 hash6: paule (SHA256)

 hash7 : n63umy8lkf4i (ntlm)

 hash 8 couldnt complete? used -m 1800 but encountered clWaitForEvents(): CL_UNKNOWN_ERROR. Online says due to hardware

 hash8 : waka99 (sha512 salted) [Uncompleted]

 hash 9 use -m 150 

 hash9 : 481616481616 (HMAC SHA1)