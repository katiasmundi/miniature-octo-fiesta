# The Booking System – Phase 2: Password Cracking

The primary tool that I used was John the Ripper (Jumbo build for Windows), supported by the widely used rockyou.txt password wordlist. I first collected all usernames and their corresponding MD5 password hashes from the database and saved them into a single hashes.txt file, using the username:hash format required by John the Ripper.

Because the instructions mentioned that four of the passwords could be solved using a dictionary attack, I began by testing that method, and the initial dictionary attack—executed with the command john.exe --format=raw-md5 --wordlist=rockyou.txt hashes.txt—immediately revealed the first four passwords due to their presence in the wordlist:

1. whatsupdoc@looneytunes.tv - carrots123
2. doh@springfieldpower.net - donuts4life
3. iamyourfather@deathstar.gov - darkside42
4. genius@starkindustries.com - iamironman

<img width="1004" height="657" alt="image" src="https://github.com/user-attachments/assets/ed883a13-06c9-4b3f-b39b-f9873d591461" />

After that I focused on recovering one of the remaining hashes by isolating it into the hashes.txt file as a single entry: darkknight@gothamwatch.org:735f7f5e652d7697723893e1a5c04d90. Based on the provided hints, I knew that the password consisted of 12 lowercase letters, and that the first six characters were “iamven”. Because this structure was partially known, a targeted mask attack was the most efficient approach. I executed the command john.exe --format=raw-md5 --mask=iamven?l?l?l?l?l?l hashes.txt, which allowed John the Ripper to brute-force only the six unknown characters instead of attempting a full-length brute-force attack. Using this method, the password successfully resolved to:

5. darkknight@gothamwatch.org - iamvengeance

<img width="1004" height="188" alt="image" src="https://github.com/user-attachments/assets/42f06fa0-2151-4305-ba0a-95ee3c8ddb18" />

Finally, I verified the results by testing all five recovered username–password pairs and confirmed that each of them allowed a successful login into the application.

<img width="1004" height="385" alt="image" src="https://github.com/user-attachments/assets/30aa9bf6-fa66-4731-a605-0539f64dbee7" />


A dictionary attack relies on predefined wordlists of common passwords, making it fast but limited, whereas non-dictionary attacks such as brute-force or mask attacks can generate all possible character combinations and therefore crack passwords that do not appear in any wordlist.

When an attacker gains access to the system’s user database and password hashes, they can perform offline cracking without rate limits, logging, or account lockouts, allowing them to attempt millions of guesses per second using tools like John the Ripper.

Longer passwords provide significantly stronger security because the search space grows exponentially with each additional character, making both dictionary and brute-force attacks far slower and often infeasible with realistic computational resources.
