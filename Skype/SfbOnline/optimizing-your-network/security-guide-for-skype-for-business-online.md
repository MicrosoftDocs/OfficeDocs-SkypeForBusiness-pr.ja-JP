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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "30493916"
---
# <a name="security-and-skype-for-business-online"></a>セキュリティとオンライン ビジネスの Skype

Skype for Business Online (SfBO), as part of the Office 365 service, follows all the security best practices and procedures such as service-level security through defense-in-depth, customer controls within the service, security hardening and operational best practices. 詳細については、マイクロソフトのセキュリティ センターを参照してください (https://microsoft.com/trustcenter)。

## <a name="trustworthy-by-design"></a>設計による高信頼性
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/en-us/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>既定による高信頼性
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>SfBO の一般的なセキュリティ上の脅威に対する対処方法
このセクションでは、SfBO サービスとマイクロソフトがそれぞれの脅威を軽減する方法のセキュリティに対する一般的な脅威を識別します。

### <a name="compromised-key-attack"></a>危殆化鍵による攻撃
キーとは、機密情報の暗号化、復号化、または検証に使用される秘密のコードまたは数値です。 考慮すべき公開キー基盤 (PKI) には、各証明書の所有者が所持する秘密キーと、通信パートナーによる ID およびセッション キーの交換が成功した後に使用されるセッション キーの 2 つの機密キーがあります。 侵害されたキーによる攻撃は、攻撃者が秘密キーまたはセッション キーを割り出した場合に発生します。 攻撃者がキーの割り出しに成功した場合、攻撃者はそのキーを使用して、データの送信者に関する知識がなくても、暗号化されているデータを解読できます。

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>ネットワークのサービス拒否攻撃
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- 攻撃対象のネットワークで実行されているアプリケーションまたはサービスに対して無効なデータを送信して、そのようなアプリケーションまたはサービスが正常に機能するのを妨害する。
- 大量のトラフィックを送信し、正当な要求に対するシステムの応答が停止または低速化するまでシステムを過負荷状態にする。
- 攻撃の証拠を隠蔽する。
- ユーザーがネットワーク リソースにアクセスできないようにする。

SfBO は、Azure DDOS ネットワークの保護を実行し、同じエンドポイント、サブネット、および連合のエンティティからのクライアント要求の調整によってこれらの攻撃を軽減します。

### <a name="eavesdropping"></a>盗聴
Eavesdropping can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called sniffing or snooping. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path. 

SfBO uses mutual TLS (MTLS) for server communications within O365 and TLS from clients to the service, rendering this attack very difficult to impossible to achieve within the time period in which a given conversation could be attacked. TLS authenticates all parties and encrypts all traffic. This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.

TURN プロトコルは、リアルタイム メディア通信に使用されます。 プロトコルを有効にする必須ではないトラフィックを暗号化して、それを送信している情報は、メッセージの整合性によって保護されています。 盗聴に開いているが、情報に送信するパケットの発信元と宛先のアドレスを見るだけで直接 (つまり、IP アドレスおよびポート) を抽出できます。 SfBO サービスにより、データがクリア テキストで送信されることはありませんを有効にするパスワードを含む、いくつかの項目から派生したキーを使用して、メッセージのメッセージの整合性を確認することで有効であります。 メディア トラフィックには SRTP を使用し暗号化されています。

### <a name="identity-spoofing-ip-address-spoofing"></a>ID のスプーフィング (IP アドレスのスプーフィング)
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- 伝送制御プロトコル (TCP) のみをサポートする接続を構成した (TCP 接続は暗号化されないため、推奨されません)。
- このような接続の IP アドレスを信頼できるホストとしてマークした 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>man-in-the-middle 攻撃
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

中間者攻撃は、TLS を使うセッション開始プロトコル (SIP) を使用してピア間でネゴシエートされた暗号キーを使用する SRTP で暗号化された SfBO Point-To-Point 音声、ビデオ、アプリケーション共有ストリームを除き、2 つのクライアント間のメディア トラフィックでも発生する可能性がありますします。 

### <a name="rtp-replay-attack"></a>RTP 再生攻撃
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>SPIM
Spim is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.

### <a name="viruses-and-worms"></a>ウイルスとワーム
ウイルスは、同種の追加コード単位の複製を目的としたコード単位です。 ウイルスは、有効に機能するためにホスト (ファイル、電子メール、プログラムなど) を必要とします。 ワームもウイルスと同様にコードの追加、複写、複製を行うプログラムですが、ウイルスとは異なりホストを必要としません。 ウイルスとワームは、クライアント間でファイルを転送しているとき、または他のユーザーから URL が送信されたときに主に出現します。 ウイルスがコンピューター上に存在する場合、そのウイルスは、たとえば、無断でユーザー ID を使用してインスタント メッセージを送信する可能性があります。 定期的なウイルス スキャンなどの標準的なクライアント セキュリティのベスト プラクティスは、この問題を軽減します。 

## <a name="personally-identifiable-information"></a>個人を特定できる情報
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***表 1 - 拡張プレゼンス データ***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **データ**             | **指定可能な****設定**                                                                  |   |
| 個人データ        | タイトル、会社名、電子メール アドレス、タイム ゾーン                                             |   |
| 電話番号    | 勤務先、携帯、自宅                                                                         |   |
| 予定表情報 | 会議の詳細 (予定表へのアクセス権を持っているもの) に、空き時間情報、Out-of-town の通知 |   |
| [プレゼンス状態]      | 退席中、連絡可能、取り込み中、応答不可、オフライン                                             |   |
|                      |                                                                                            |   |

<!-- end of table -->

***表 2 - 必須データ***

<!--start table here -->


|              |                                                                 |   |
|:-------------|:----------------------------------------------------------------|:--|
| **[カテゴリ]** | **使用可能な設定**                                           |   |
| IP アドレス   | コンピューターの実際のアドレスまたは NAT で変換したアドレス                     |   |
| SIP URI      | <u>david.campbell@contoso.com</u>                               |   |
| 名前         | (定義されている Active Directory ドメイン サービスで)、久保田隆 |   |
|              |                                                                 |   |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>SfBO のセキュリティ フレームワーク
This section provides an overview of the fundamental elements that form the security framework for Microsoft SfBO. These elements are as follows:
- Azure Active Directory (AAD) は、ユーザー アカウント用の単一の信頼できるバックエンド リポジトリを提供します。 
- 公開キー基盤 (PKI) は、サーバーの認証し、データの整合性を確保する、信頼された証明機関 (Ca) によって発行された証明書を使用します。
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- ユーザーの認証には、業界標準のプロトコルができる限り使用されます。

このセクションのトピックでは、SfBO サービスのセキュリティを強化するためにこれらの基本的な要素の動作方法について説明します。

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory functions as the directory service for O365. It stores all user directory information and policy assignments. 

### <a name="public-key-infrastructure-for-sfbo"></a>SfBO の公開キー基盤
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>CRL 配布ポイント
SfBO には、1 つまたは複数の証明書失効リスト (CRL) 配布ポイントを格納するためのすべてのサーバー証明書が必要です。 CRL 配布ポイント (CDP) とは、証明書の発行後にそれが失効していないこと、および証明書が有効期限内にあることを確認するために、CRL をダウンロードできる場所です。 CRL 配布ポイントでは、URL として証明書のプロパティに記録され、セキュリティで保護された http です。 SfBO サービスは、すべての証明書認証で CRL を確認します。

#### <a name="enhanced-key-usage"></a>拡張キー使用法
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
|インスタント メッセージングとプレゼンス|TLS (TLS用に設定されている場合)|
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
O365 の AAD によって認証された資格情報が信頼されたユーザーとは。 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **先進認証 (MA)** は、クライアントとサーバー間の通信用に Microsoft が OAUTH 2.0 を実装したものです。 O365 証明書ベースの認証、O365 マルチ ファクター認証、O365 条件付きアクセスなどのセキュリティ機能を有効にします。 MA を使用するには、オンライン テナントとクライアントの両方で MA が有効にされている必要があります。 2017 年 5 月以降に作成された SfBO テナントでは、MA は既定値として有効になっています。 これ以前に作成されたテナントの場合は、指示に従って有効にします。 Skype for Business 2015 または 2016 クライアント、Skype for Business on Mac、Lync 2013 クライアント、3PIP IP 電話、iOS、Android のすべてのクライアントは MA に対応しています。 
- 現代の認証は有効になっている (使用できない) 場合は、**組織の ID**が使用されます。
- **ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。

SfBO 認証は、2 つのフェーズで構成されます。
1. クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。
2. クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

クライアント証明書は、SfBO で認証されるユーザーに対して別の方法を提供します。ユーザーでは、ユーザー名とパスワードを提供することではなく証明書と暗号化の課題を解決するために必要な証明書に対応する秘密キーがあります。 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Windows PowerShell と SfBO 管理ツール
SfBO では、IT 管理者は O365 管理ポータルまたはテナント リモート パワーシェル (TRPS) を使用してサービスを管理できます。 テナント管理者は先進認証を使用して TRPS を認証します。

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>インターネット境界で SfBO へのアクセスを設定する
(ユーザーなどの会議に参加すること)、お客様のニーズ、インターネットを構成するのには適切に機能する SfBO の SfBO の雲の中のサービスへ送信された UDP および TCP トラフィックを許可するようにアクセスします。 詳細については、ここで参照してください。https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478 〜 3481 と TCP 443

443 の TCP ポートと UDP 3478-3481 クライアントが使用、A からのサービスを要求すると音声ビデオ エッジ サービスです。クライアントでは、これらの 2 つのポートに UDP を割り当てると、相手のそれぞれの TCP ポートを使用してに接続します。A にアクセスすると、音声ビデオ エッジ サービスでは、クライアントする必要があります最初確立 A を入手するのには SfBO のレジストラーとのセッションを通知する認証済みの SIP 音声ビデオ エッジ サービスの認証の資格情報です。これらの値は、TLS で保護された信号チャネルを経由して送信され、辞書攻撃を緩和するために生成されたコンピューターです。クライアントが A とダイジェスト認証にこれらの資格情報を使用して音声ビデオ エッジ サービスのメディア ・ セッションで使用するためのポートを割り当てることです。最初の割り当て要求がクライアントから送信され、A から 401 nonce/チャレンジ メッセージで応答または音声ビデオ エッジ サービスです。クライアントから 2 番目の割り当て、ユーザー名とハッシュ メッセージ認証コード (HMAC) を含むユーザー名と nonce のハッシュです。 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP と TCP の 50,000 – 59,999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>外部ユーザー音声ビデオ トラフィック トラバーサル
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![会議参加のコール シーケンス](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>ユーザーは、ユーザーの機器上でクライアント検出プロセスを開始する電子メール内の会議 URL をクリックすることにより、参加手順を開始します。 検出されたクライアントが起動します。 クライアントが検出されない場合、ユーザーは Web クライアントにリダイレクトされます。<p/>
2. SfBO クライアントは、ユーザーの資格情報を含む SIP INVITE を送信します。 フェデレーションまたはリモート ユーザーは、エンタープライズ資格情報を使用して会議に参加します。 フェデレーション ユーザーの場合、SIP INVITE はまずユーザーを認証し、INVITE を SfBO に転送する自身のホーム サーバーに送信されます。 匿名ユーザーは、ダイジェスト認証に通る必要があります。<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. クライアントは、音声ビデオ会議にユーザーを追加するために INFO リクエストを送信します。

    A V 会議、A に提示するトークンが含まれている追加のユーザー応答を送信する/V 会議エッジ サービスの他の情報。

    [メモ] 上記のすべての SIP トラフィックは、アクセス エッジ サービスを介して流し込まれます。

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. クライアントと A の間 V 会議サーバー、メディアの接続のネゴシエーションを行うと、SRTP 経由のセットアップ。
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>SfBO のフェデレーション セーフガード
フェデレーションは、組織が IM とプレゼンスを共有するために他の組織と通信する機能を提供します。 SfBO では、フェデレーションは既定で有効です。 ただし、テナント管理者は O365 管理ポータルでこれをコントロールできます。 続きを見る。

## <a name="addressing-threats-to-sfbo-conferences"></a>SfBO 会議の脅威に対する取り組み

SfBO provides the capability for enterprise users to create and join real-time Web conferences. Enterprise users can also invite external users who do not have an AAD/O365 account to participate in these meetings. Users who are employed by federated partners with a secure and authenticated identity can also join meetings and, if promoted to do so, can act as presenters. Anonymous users cannot create or join a meeting as a presenter, but they can be promoted to presenter after they join.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- 参加者の役割により会議通話のコントロール権限が決定します。
- 参加者タイプの使用により、特定の会議へのアクセスを制限できます。
- 会議の種類を定義することで、参加可能な参加者のタイプが決まります。
- 会議をスケジュールできるのは、AAD アカウントと SfBO ライセンスを持つユーザーに限定されます。
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>参加者の役割
会議の参加者は 3 つのグループに分けられ、それぞれ権限と制限があります。
- **開催者**&nbsp; &nbsp;Impromptu またはスケジュールすることによって、かどうか、会議を作成するユーザーです。 会議の開催者は、認証済みのエンタープライズ ユーザーである必要があり、会議のすべてのエンド ・ ユーザーの側面を制御します。
- **発表者**&nbsp;&nbsp;どのようなメディアのサポートを使用して、会議で情報を表示する権限があるユーザーです。 会議の開催者は、定義上のプレゼンターでもあり、他に誰がプレゼンターになれるかを決定します。 開催者は、会議をスケージュールした時、または会議の進行中にこの決定を行えます。
- **出席者**&nbsp;&nbsp;ユーザーが会議に出席に招待されている者、発表者として機能する権限がありません。

プレゼンターは、会議の進行中に出席者にプレゼンターの役割を与えることもできます。

### <a name="participant-types"></a>参加者タイプ

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **テナントに属しているユーザー**&nbsp; &nbsp;、テナントの Azure Active Directory の資格情報があるこれらのユーザーです。<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **テナントに属するユーザー** &nbsp;&nbsp; これらのユーザーは、テナントのAzure Active Directoryに資格情報を持っています。<br/>a.*フェデレーション ユーザー*にフェデレーション ユーザーは、フェデレーション パートナーとの有効な資格情報を持っているし、SfBO によって認証されるように扱われますので。フェデレーション ユーザーは会議に参加することができ、ミーティングに参加した後、フェデレーションには、企業の会議を作成することはできません、発表者に昇格します。<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>参加者入場許可
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

既定の設定では、PSTN からダイヤルインする参加者は直接会議に入りますが、このオプションを変更してダイヤルイン参加者も強制的にロビーに転送することができます。  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **会議の開催者である自分のみ**&nbsp;&nbsp;開催者を除くすべての参加者は、許可されるまでロビーで待機する必要があります。
- **会社内から招待した人**&nbsp;&nbsp;社内の誰でも、たとえ招待されていない場合でも、直接会議に参加できます。
- **Anyone from my organization**&nbsp;&nbsp;All SfBO users in the O365 tenant can join the meeting without waiting in the lobby, even if those who are not on the distribution list. All others, including all external and anonymous users, must wait in the lobby until admitted.
- **誰でも**&nbsp;&nbsp;の会議出席依頼に直接の人 (制限はありません)、会議のリンクへのアクセスを取得します。
開催者のみ (ロック済み) 以外の方法が指定されている場合、会議の開催者はロビーで待機せず電話でダイヤルインするユーザーを指定することもできます。 

### <a name="presenter-capabilities"></a>プレゼンターの指定
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **開催者のみ**&nbsp;&nbsp;会議の開催者のみを表示できます。
- **自分の会社から人**&nbsp;&nbsp;内部のすべてのユーザーを表示できます。
- **自分の会社の外部のユーザーも含めてだれも**&nbsp;&nbsp;表示すべてのユーザー (制限はありません)、ミーティングに参加することができます。
- **指定した人**&nbsp;&nbsp;会議の開催者がプレゼンターになることができるユーザーを指定します。

## <a name="related-topics"></a>関連項目
[マイクロソフトのセキュリティ センター](https://microsoft.com/trustcenter)

