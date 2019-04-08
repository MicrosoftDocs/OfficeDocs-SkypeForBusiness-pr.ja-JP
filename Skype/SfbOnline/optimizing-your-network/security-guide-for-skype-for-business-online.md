---
title: Skype for Business Online セキュリティ ガイド
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: ''
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Security
description: Skype for Business Online セキュリティ ガイド <add description>
ms.openlocfilehash: 555a7bd3e4a57c637c0375ea406caeca3c221be7
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "30493916"
---
# <a name="security-and-skype-for-business-online"></a>セキュリティと Skype for Business Online

Skype for Business Online (SfBO), as part of the Office 365 service, follows all the security best practices and procedures such as service-level security through defense-in-depth, customer controls within the service, security hardening and operational best practices. For full details, please see the Microsoft Trust Center (https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>設計による高い信頼性
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/en-us/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>既定による高い信頼性
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>SfBO の一般的なセキュリティ上の脅威に対する対処方法
このセクションでは、SfBO サービスのセキュリティに対するより一般的な脅威と、Microsoft がそれらの脅威の軽減に用いる方法を明らかにします。

### <a name="compromised-key-attack"></a>危害を受けたキーによる攻撃
キーとは、機密情報の暗号化、復号化、または検証に使用される秘密のコードまたは数値です。公開キー基盤 (PKI) で使用される、注意が必要な機密のキーは 2 つあります。1 つは各証明書所有者が持つ秘密キーで、もう 1 つは通信するパートナーによる識別とセッション キーの交換が成功した後で使用されるセッション キーです。侵害されたキーによる攻撃は、攻撃者が秘密キーまたはセッション キーを割り出した場合に発生します。攻撃者がキーを割り出すのに成功した場合、攻撃者はそのキーを使用して、データの送信者に関する知識がなくても、暗号化されているデータを復号化できます。

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>ネットワークのサービス拒否攻撃
サービス拒否攻撃は、有効なユーザーによるネットワークの正常な使用または機能が、攻撃者によって妨害された場合に発生します。サービス拒否攻撃により、攻撃者は以下のことを行うことができます。
- 攻撃対象のネットワークで実行されているアプリケーションまたはサービスに対して無効なデータを送信して、そのようなアプリケーションまたはサービスが正常に機能するのを妨害する。
- 大量のトラフィックを送信してシステムを過負荷状態にして、適正な要求に対するシステムの応答を停止または低速化する。
- 攻撃の証拠を隠蔽する。
- ユーザーがネットワーク リソースにアクセスできないようにする。

このような攻撃を緩和するため、SfBO は Azure DDOS ネットワーク保護を実行し、同じエンドポイント、サブネット、およびフェデレーション エンティティからのクライアント要求を調整します。

### <a name="eavesdropping"></a>盗聴
盗聴は、攻撃者が、ネットワークのデータ パスにアクセスし、トラフィックの監視と読み取りの機能を持っているときに起こる可能性があります。これは、スニッフィングまたはスヌーピングとも呼ばれます。トラフィックがプレーン テキストの場合、攻撃者は、ネットワークのパスにアクセスしたときにトラフィックを読み取ることができます。例としては、データ パス上のルーターを制御することによって実行される攻撃があります。 

SfBO uses mutual TLS (MTLS) for server communications within O365 and TLS from clients to the service, rendering this attack very difficult to impossible to achieve within the time period in which a given conversation could be attacked. TLS authenticates all parties and encrypts all traffic. This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.

The TURN protocol is used for real time media purposes. The TURN protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity. Although it is open to eavesdropping, the information it is sending (that is, IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets. The SfBO service ensures that the data is valid by checking the Message Integrity of the message using the key derived from a few items including a TURN password, which is never sent in clear text. SRTP is used for media traffic and is also encrypted.

### <a name="identity-spoofing-ip-address-spoofing"></a>ID のスプーフィング (IP アドレスのスプーフィング)
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- 伝送制御プロトコル (TCP) のみをサポートする接続を構成した (TCP 接続は暗号化されないため、推奨されません)。
- このような接続の IP アドレスを信頼されたホストとしてマークした。 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>中間者攻撃
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

中間者攻撃は、TLS を使うセッション開始プロトコル (SIP) を使用してピア間でネゴシエートされた暗号キーを使用する SRTP で暗号化された SfBO Point-To-Point 音声、ビデオ、アプリケーション共有ストリームを除き、2 つのクライアント間のメディア トラフィックでも発生する可能性がありますします。 

### <a name="rtp-replay-attack"></a>RTP リプレイ アタック
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>SPIM
SPIM とは、一方的に送りつけられる営利目的のインスタント メッセージまたはプレゼンス サブスクリプション要求のことです。それ自体はネットワークを侵害するものではありませんが、少なくとも迷惑なものであり、リソースの可用性および生産性を低下させ、結果としてネットワークの侵害を招く可能性があります。SPIM の一例として、ユーザーが要求を送信することで相互に SPIM を送るケースがあります。ユーザーは相互にブロックしてこれを防ぐことができますが、フェデレーションの場合、調整された SPIM 攻撃が確立されると、パートナーのフェデレーションを無効にしない限り、対処が困難になるおそれがあります。

### <a name="viruses-and-worms"></a>ウイルスとワーム
A virus is a unit of code whose purpose is to reproduce additional, similar code units. To work, a virus needs a host, such as a file, email, or program. Like a virus, a worm is a unit of code that is coded to reproduce additional, similar code units, but that unlike a virus does not need a host. Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users. If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf. Standard client security best practices such as periodically scanning for viruses can mitigate this issue. 

## <a name="personally-identifiable-information"></a>個人を特定できる情報
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***表 1 - 拡張プレゼンス データ***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **データ**             | **指定可能な****設定**                                                                  |   |
| 個人データ        | 名前、役職、会社、電子メール アドレス、タイム ゾーン                                             |   |
| 電話番号    | 勤務先、携帯、自宅                                                                         |   |
| 予定表情報 | 空き時間、出張の通知、ミーティングの詳細 (予定表にアクセスできるユーザーに公開されます) |   |
| [プレゼンス状態]      | 退席中、連絡可能、取り込み中、応答不可、オフライン                                             |   |
|                      |                                                                                            |   |

<!-- end of table -->

***表 2 - 必須データ***

<!--start table here -->


|              |                                                                 |   |
|:-------------|:----------------------------------------------------------------|:--|
| **カテゴリ** | **指定可能な設定**                                           |   |
| IP アドレス   | コンピューターの実際のアドレスまたは NAT で変換したアドレス                     |   |
| SIP URI      | <u>david.campbell@contoso.com</u>                               |   |
| 名前         | David Campbell (Active Directory Domain Services で定義されている名前) |   |
|              |                                                                 |   |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>SfBO のセキュリティ フレームワーク
This section provides an overview of the fundamental elements that form the security framework for Microsoft SfBO. These elements are as follows:
- Azure Active Directory (AAD) は、ユーザー アカウント用の単一の信頼できるバックエンド リポジトリを提供します。 
- 公開キー基盤 (PKI) は、信頼された証明機関 (CA) によって発行された証明書を使用してサーバーを認証し、データの整合性を確保します。
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- ユーザーの認証には、業界標準のプロトコルができる限り使用されます。

このセクションのトピックでは、SfBO のセキュリティを高めるために、各基本要素が機能するしくみについて説明します。

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory functions as the directory service for O365. It stores all user directory information and policy assignments. 

### <a name="public-key-infrastructure-for-sfbo"></a>SfBO の公開キー基盤
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>CRL 配布ポイント
SfBO requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points. CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period. A CRL distribution point is noted in the properties of the certificate as a URL and is secure HTTP. The SfBO service checks CRL with every certificate authentication.

#### <a name="enhanced-key-usage"></a>拡張キーの使用方法
All components of the SfBO service require all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication. Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers. This EKU is essential for MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>SfBO の TLS と MTLS
TLS and MTLS protocols provide encrypted communications and endpoint authentication on the Internet. SfBO uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted. All SIP communications between servers occur over MTLS. SIP communications from client to server occur over TLS.

TLS enables users, through their client software, to authenticate the SfBO servers to which they connect. On a TLS connection, the client requests a valid certificate from the server. To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate. If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication. The resulting connection is trusted and from that point is not challenged by other trusted servers or clients. Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.

Server-to-server connections rely on mutual TLS (MTLS) for mutual authentication. On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA. The certificates prove the identity of each server to the other. In the SfBO service, this procedure is followed.

TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks. In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party. TLS and SfBO’s specification of trusted servers mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication. 

### <a name="encryption-for-sfbo"></a>SfBO の暗号化
SfBO uses TLS and MTLS to encrypt instant messages. All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.

次の表は、SfBO で使用するプロトコルをまとめたものです。

***表 3 - トラフィック保護***

<!--start table here with header -->


|||
|:-----|:-----|
|**トラフィックの種類**|**保護用プロトコル**|
|サーバー間|MTLS|
|クライアントからサーバー|TLS|
|インスタント メッセージングとプレゼンス|TLS (TLS 用に構成されている場合)|
|オーディオとビデオ、メディアのデスクトップ共有|SRTP|
|デスクトップ共有 (シグナリング)|TLS|
|Web 会議|TLS|
|会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張|HTTPS|
|||

<!-- end of table -->

#### <a name="media-encryption"></a>メディアの暗号化
Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. SRTP uses a session key generated by using a secure random number generator and exchanged using the signaling TLS channel. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. 

SfBO generates username/passwords for secure access to media relays over TURN. Media relays exchange the username/password over a TLS-secured SIP channel.

#### <a name="fips"></a>FIPS
SfBO は、暗号キーの交換に FIPS (Federal Information Processing Standard) に準拠したアルゴリズムを使用します。 

### <a name="user-and-client-authentication"></a>ユーザー認証とクライアント認証 
信頼されたユーザーとは、AAD in O365 によって資格情報が認証されたユーザーを指します。 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **Modern Authentication** is the Microsoft implementation of OAUTH 2.0 for client to server communication. It enables security features such as O365 Certificate Based Authentication, O365 Multi-Factor Authentication and O365 Conditional Access. In order to use MA, both the online tenant and the clients need to be enabled for MA. SfBO tenants created after May 2017 have MA enabled by default. For tenants created before this time, follow the instructions here to turn it on. The following clients all support MA: Skype for Business 2015 or 2016 client, Skype for Business on Mac, Lync 2013 client, 3PIP IP Phones, iOS, and Android. 
- **Org ID** は、先進認証が有効ではない (または使用できない) 場合に使用されます。
- **ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。

SfBO 認証は 以下の 2 つのフェーズで構成されます。
1. クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。
2. クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

Client certificates provide an alternate way for users to be authenticated by SfBO. Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Windows PowerShell と SfBO 管理ツール
In SfBO, IT Admins can manage their service via the O365 Admin portal or by using Tenant Remote PowerShell (TRPS). Tenant admins use Modern Authentication to authenticate to TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>インターネット境界で SfBO へのアクセスを設定する
For SfBO to function properly (users able to join meetings etc.), customers need to configure their internet access such that outbound UDP and TCP traffic to services in the SfBO cloud is allowed. For more details, see here: https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478 〜 3481 と TCP 443

The UDP 3478-3481 and TCP 443 ports are used by clients to request service from the A/V Edge service. A client uses these two ports to allocate UDP and TCP ports respectively for the remote party to connect to. To access the A/V Edge service, the client must first have established an authenticated SIP signaling session with SfBO registrar to obtain A/V Edge service authentication credentials. These values are sent across the TLS-protected signaling channel and are computer generated to mitigate against dictionary attacks. Clients can then use these credentials for digest authentication with the A/V Edge service to allocate ports for use in a media session. An initial allocate request is sent from the client and responded with a 401 nonce/challenge message from the A/V Edge service. The client sends a second allocate containing the user name and a Hash Message Authentication Code (HMAC) hash of the user name and nonce. 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP/TCP 50,000～59,999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>外部ユーザーの音声ビデオ トラフィックのトラバース
外部ユーザーと内部ユーザーの間でメディアを交換できるようにするには、セッションのセットアップおよび切断に必要な SIP シグナリングを処理するアクセス エッジ サービスが必要です。また、音声ビデオ エッジ サービスをメディア転送用のリレー機能として使用する必要もあります。次の図に、呼び出しシーケンスを示します。


![会議参加のコール シーケンス](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>The user initiates the join procedure by clicking the meeting URL in the email which initiates a client detection process on the user’s machine. If the client is detected, this client is launched.  If it is not detected, the user is redirected to the web client.<p/>
2. The SfBO client sends a SIP INVITE containing the user’s credentials. A federated or remote user joins a conference using their enterprise credentials. For a federated user, the SIP INVITE is first sent to his or her home server, which authenticates the user and forwards the INVITE to SfBO. An anonymous user is required to pass digest authentication.<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. クライアントは、音声ビデオ会議にユーザーを追加するために INFO リクエストを送信します。

    A/V 会議によって、A/V 会議エッジ サービスに提示するトークンおよびその他の情報を含むユーザーの追加応答が送信されます。

    [注意] 前の SIP トラフィックはすべて、アクセス エッジ サービスを介して送信されます。

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. クライアントと A/V 会議サーバー間で、メディア接続のネゴシエーションを行うと、SRTP でセットアップされます。
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>SfBO のフェデレーション保護対策
Federation provides your organization with the ability to communicate with other organizations to share IM and presence. In SfBO federation is on by default. However, tenant admins have the ability to control this via the O365 Admin portal. See more.

## <a name="addressing-threats-to-sfbo-conferences"></a>SfBO 会議の脅威に対する取り組み

SfBO provides the capability for enterprise users to create and join real-time Web conferences. Enterprise users can also invite external users who do not have an AAD/O365 account to participate in these meetings. Users who are employed by federated partners with a secure and authenticated identity can also join meetings and, if promoted to do so, can act as presenters. Anonymous users cannot create or join a meeting as a presenter, but they can be promoted to presenter after they join.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- 電話会議の制御特権を参加者の役割に応じて割り当てます。
- 参加者の種類別に特定の会議へのアクセスを制限できます。
- どの会議にどの種類の参加者が出席できるかは、定義されている会議の種類によって決まります。
- 会議をスケジュールできるのは、AAD アカウントと SfBO ライセンスを持つユーザーに限定されます。
- ダイヤルイン電話会議に参加する匿名ユーザー (未認証ユーザー) が、電話会議のアクセス番号の 1 つをダイヤルすると、電話会議 ID を入力するように指示されます。このとき、認証されていない匿名ユーザーは、名前も録音する必要があります。電話会議に出席中の認証されていないユーザーは、この録音された名前によって識別されます。主催者または認証済みユーザーが少なくとも 1 名参加するまで、匿名ユーザーは電話会議への参加が許可されません。また、匿名ユーザーには事前に定義された役割も割り当てられません。

### <a name="participant-roles"></a>参加者の役割
会議参加者は 3 つのグループに分類され、以下のようにそれぞれに独自の特権と制限があります。
- **開催者** &nbsp;&nbsp;会議を作成するユーザー (今すぐ開始する会議を作成することも、会議を予約することも可能)。開催者は、認証済みエンタープライズ ユーザーである必要があり、会議のエンド ユーザーのあらゆる面を制御できます。
- **発表者** &nbsp;&nbsp;サポートされている任意のメディアを使用して会議で発表することが承認されているユーザー。定義上、会議の開催者は発表者でもあり、別の発表者を指定します。発表者の指定は、会議の予約時に行うことも、会議中に行うこともできます。
- **参加者** &nbsp;&nbsp;会議に招待されているが、発表者になることは承認されていないユーザー。

発表者は、会議中に参加者を発表者に昇格することもできます。

### <a name="participant-types"></a>参加者の種類

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **テナントに属するユーザー** &nbsp;&nbsp;これらのユーザーは、テナントの Azure Active Directory に資格情報を持っています。<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **テナントに属するユーザー** &nbsp;&nbsp; これらのユーザーは、テナントのAzure Active Directoryに資格情報を持っています。<br/>a. *Federated Users* - Federated users possess valid credentials with federated partners and are therefore treated as authenticated by SfBO. Federated users can join conferences and be promoted to presenters after they have joined the meeting, but they cannot create conferences in enterprises with which they are federated.<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>参加者の許可
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

既定の設定では、PSTN からダイヤルインする参加者は直接会議に入りますが、このオプションを変更してダイヤルイン参加者も強制的にロビーに転送することができます。  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **会議の開催者である自分のみ**&nbsp;&nbsp;開催者を除くすべての参加者は、許可されるまでロビーで待機する必要があります。
- **会社内から招待した人**&nbsp;&nbsp;社内の誰でも、たとえ招待されていない場合でも、直接会議に参加できます。
- **Anyone from my organization**&nbsp;&nbsp;All SfBO users in the O365 tenant can join the meeting without waiting in the lobby, even if those who are not on the distribution list. All others, including all external and anonymous users, must wait in the lobby until admitted.
- **Anyone**&nbsp;&nbsp;Anyone (there are no restrictions) who has access to the meeting link gets in to the meeting directly. When any method except Organizer only (locked) is specified, the meeting organizer can also specify People dialing in by phone bypass the lobby. 

### <a name="presenter-capabilities"></a>発表者の機能
会議の開催者は、参加者が会議中に発表できるかどうかを制御します。会議ごとに、発表者を次のいずれかに制限できます。
- **開催者のみ**&nbsp;&nbsp; 会議の開催者のみが発表できます。
- **会社内の人**&nbsp;&nbsp; すべての内部ユーザーが発表できます。
- **会社外の人を含むすべての人**&nbsp;&nbsp; 会議に参加するすべての人がプレゼンターになれます (制限はありません)。
- **指定した人**&nbsp;&nbsp;会議の開催者がプレゼンターになることができるユーザーを指定します。

## <a name="related-topics"></a>関連トピック
[Microsoft Trust Center](https://microsoft.com/trustcenter)

