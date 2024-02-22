# Basics on Information Security & Privacy 

## AI-based assistants

SoTA:
- not fully developed( i.e. the delivered answers are not necessarily correct)
- some assistants (e.g., ChatGPT) use all data for ML (send the entered information to servers)
  $\implies$ they can provide data entered by you in response to (external) users' queries

Usage of AI-based assistants:
- rules:
    1. Don't input **confidential data**
    2. Don't input **personal data** (reason: might violate [GDPR](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) & other laws)
    3. **Critically reviewed (not accepted unchecked)** responses
       (reason: no guarantee of correctness for delivered answers)
    4. Pay attention to the aspects of **copyright and open source licenses**
- application areas:
  - text-based AI assistants
  - image generation
  - publicly available internet services (e.g., translation engines)

AI systems vulnerabilities:
- classic cyber security threats
- specific AI-threats (e.g., model vulnerabilities)

## Cyber-safety at home

Rules for confidential info:
- turn off smart speakers/voice assistants (Alexa, Siri, etc)
- print only at secured printers (printers are easy to hack)
- only known VPN connections
- only secure laptop
- avoid private accessories

Security **goals**:
- **Confidentiality**
  - secure passwords:
    1. *at least 12 characters* consisting of lower-case letters, upper case letters and numbers;
       terms that *do not appear in dictionaries* or are easy to guess
    2. *Never give* your password to someone else (including IT admin)
    3. Use *different passwords everywhere*
    4. *Change immediately if* you *suspect* disclosure
    5. *manage passwords* (e.g., with the password manager like [KeePass](https://www.intranet.bosch.com/doku/isp_public/ISP_Trainings/ISP001/Redirect_ISP001_KeePass.html))
- **Availability**
- **Integrity**

## Personal data 

- personal data: anything that can be attributed to a person
  - examples:
    - obvious: name, address or birth date
    - less obvious: IP address, vehicle ID, personal internet reviews, etc
    - *more sensitive*: health data, political opinions, sexual orientation, biometric or genetic data
  - rules:
    1. processed $\iff$ $\exists$ *legal basis* (a contract or the consent of the person) and a *purpose* (marketing or salary payments) for its use
    2. no longer required and no obligation to retain $\implies$ *must be deleted*
    3. *risk of high fines* if personal data is not processed in accordance with the law

## Social engineering

**Principle**: exploit the victim's good faith and helpfulness

**Variants** of social engineering:
- **phishing**: nowadays professional, targeted and difficult to understand
  1. Never click on a link, do not scan a QR code or open an attachment in a *suspicious email*
  2. Do not be *pressured*: always an *alarm signal* in which you should take a step back and rethink
  3. Always *check the sender* and *link address*, especially when prompted to enter your user data
- Vishing ('Voice Phishing'): telephone variant of Phishing
- CEO fraud: pretends to be your boss
- Quishing (QR code + Phishing):
  scanning the QR code that redirects to a website (downloads malware or steals sensitive information)

Alarm bells
1. real urgency
2. supposedly you are the only person that can help
3. ask for confidential information or money
