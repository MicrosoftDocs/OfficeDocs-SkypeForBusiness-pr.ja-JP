---
title: 'Lync Server 2013: モダンなコンピューティングでの一般的なセキュリティの脅威'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e17f9f6dbba30697c72fecf77fbff4bfbdc003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="03669-102">今日のコンピューティング環境における一般的なセキュリティの脅威</span><span class="sxs-lookup"><span data-stu-id="03669-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03669-103">_**最終更新日:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="03669-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="03669-104">Lync Server 2013 はエンタープライズクラスの通信システムであるため、インフラストラクチャと通信に影響を与える可能性のある一般的なセキュリティ攻撃について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="03669-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="03669-105">危殆化鍵による攻撃</span><span class="sxs-lookup"><span data-stu-id="03669-105">Compromised-Key Attack</span></span>

<span data-ttu-id="03669-p101">キーとは、機密情報の暗号化、復号化、または検証に使用される秘密のコードまたは数値です。公開キー基盤 (PKI) で使用される、注意が必要な機密のキーは 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="03669-p101">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information. There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="03669-108">1 つは各証明書所有者が持つ秘密キーで、</span><span class="sxs-lookup"><span data-stu-id="03669-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="03669-109">もう 1 つは通信するパートナーによる識別とセッション キーの交換が成功した後で使用されるセッション キーです</span><span class="sxs-lookup"><span data-stu-id="03669-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="03669-p102">侵害されたキーによる攻撃は、攻撃者が秘密キーまたはセッション キーを割り出した場合に発生します。攻撃者がキーを割り出すのに成功した場合、攻撃者はそのキーを使用して、データの送信者に関する知識がなくても、暗号化されているデータを復号化できます。</span><span class="sxs-lookup"><span data-stu-id="03669-p102">A compromised-key attack occurs when the attacker determines the private key or the session key. When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="03669-112">Lync Server 2013 は、Windows Server オペレーティングシステムの PKI 機能を使用して、トランスポート層セキュリティ (TLS) 接続の暗号化に使用されるキーデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="03669-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="03669-113">メディアの暗号化に使用されるキーは、TLS 接続を介して交換されます。</span><span class="sxs-lookup"><span data-stu-id="03669-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="03669-114">ネットワークのサービス拒否攻撃</span><span class="sxs-lookup"><span data-stu-id="03669-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="03669-p104">*サービス拒否攻撃*は、有効なユーザーによるネットワークの正常な使用または機能が、攻撃者によって妨害された場合に発生します。この攻撃では、正当なユーザーによるサービスの使用を圧倒するために、攻撃者がサービスに対する正当な要求を氾濫させます。サービス拒否攻撃により、攻撃者は以下のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="03669-p104">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users. This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users. By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="03669-118">攻撃対象のネットワークで実行されているアプリケーションまたはサービスに対して無効なデータを送信して、そのようなアプリケーションまたはサービスが正常に機能するのを妨害する。</span><span class="sxs-lookup"><span data-stu-id="03669-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="03669-119">大量のトラフィックを送信してシステムを過負荷状態にして、適正な要求に対するシステムの応答を停止または低速化する。</span><span class="sxs-lookup"><span data-stu-id="03669-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="03669-120">攻撃の証拠を隠蔽する。</span><span class="sxs-lookup"><span data-stu-id="03669-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="03669-121">ユーザーがネットワーク リソースにアクセスできないようにする。</span><span class="sxs-lookup"><span data-stu-id="03669-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="03669-122">盗聴 (スニッフィング、スヌーピング)</span><span class="sxs-lookup"><span data-stu-id="03669-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="03669-p105">*盗聴*は、攻撃者が、ネットワークのデータ パスにアクセスし、トラフィックの監視と読み取りの機能を持っているときに起こる可能性があります。これは、*スニッフィング*または*スヌーピング*とも呼ばれます。トラフィックがプレーン テキストの場合、攻撃者は、ネットワークのパスにアクセスしたときにトラフィックを読み取ることができます。例としては、データ パス上のルーターを制御することによって実行される攻撃があります。</span><span class="sxs-lookup"><span data-stu-id="03669-p105">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called *sniffing* or *snooping*. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="03669-127">Microsoft Lync Server 2013 内のトラフィックに対する既定の推奨事項と設定は、クライアント間の信頼されたサーバーと TLS の間で相互 TLS (MTLS) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="03669-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="03669-128">この防護対策によって、ある会話の時間内にこの攻撃を達成することは非常に困難で、不可能に近くなります。</span><span class="sxs-lookup"><span data-stu-id="03669-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="03669-129">TLS はすべての関係者を認証し、すべてのトラフィックを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="03669-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="03669-130">これで盗聴が防がれることはありませんが、攻撃者は暗号を破らない限りトラフィックを読み取れません。</span><span class="sxs-lookup"><span data-stu-id="03669-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="03669-p107">Traversal Using Relay NAT (TURN) プロトコルでは、トラフィックの暗号化は必須ではなく、送信する情報は、メッセージの整合性によって保護されます。盗聴にさらされているにもかかわらず、パケットのソースと宛先のアドレスを見るだけで、送信する情報 (つまり、IP アドレスとポート) を直接抽出できます。音声ビデオ エッジ サービスは、クリア テキストで送信されることのない TURN パスワードをはじめとするいくつかのアイテムから得られるキーを使用して、メッセージのメッセージ整合性を確認することにより、データが有効であることを確保します。Secure Real Time Protocol (SRTP) を使用すると、メディア トラフィックも暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="03669-p107">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity. Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets. The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text. If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="03669-135">ID のスプーフィング (IP アドレスのスプーフィング)</span><span class="sxs-lookup"><span data-stu-id="03669-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="03669-136">*スプーフィング*は、攻撃者が権限なしにネットワーク、コンピューター、またはネットワーク コンポーネントの IP アドレスを特定し、使用する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="03669-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="03669-137">攻撃に成功した場合、攻撃者は、通常その IP アドレスで識別されるエンティティであるかのように振る舞うことができます。</span><span class="sxs-lookup"><span data-stu-id="03669-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="03669-138">この状況は、Microsoft Lync Server 2013 のコンテキスト内で、管理者が次の両方の操作を行った場合にのみ、再生されます。</span><span class="sxs-lookup"><span data-stu-id="03669-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="03669-139">伝送制御プロトコル (TCP) のみをサポートする接続を構成した (TCP 接続は暗号化されないため、推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="03669-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="03669-140">このような接続の IP アドレスを信頼されたホストとしてマークした。</span><span class="sxs-lookup"><span data-stu-id="03669-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="03669-141">トランスポート層セキュリティ (TLS) 接続では、TLS がすべての関係者を認証し、すべてのトラフィックを暗号化するため、このような問題は生じません。</span><span class="sxs-lookup"><span data-stu-id="03669-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="03669-142">TLS を使用すると、特定の接続 (相互 TLS 接続など) で攻撃者が IP アドレス スプーフィングを実行できません。</span><span class="sxs-lookup"><span data-stu-id="03669-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="03669-143">ただし、攻撃者が Lync Server 2013 で使用される DNS サーバーのアドレスになりすましてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03669-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="03669-144">ただし、Lync の認証は証明書を使用して実行されるため、攻撃者は、通信でいずれかの当事者をスプーフィングするために必要な有効な証明書を持っているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="03669-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="03669-145">man-in-the-middle 攻撃</span><span class="sxs-lookup"><span data-stu-id="03669-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="03669-146">中間者攻撃は、攻撃者が 2 人の通信ユーザー間の通信を双方に気づかれることなく攻撃者のコンピュータを介するように再ルーティングすることで行われます。</span><span class="sxs-lookup"><span data-stu-id="03669-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="03669-147">攻撃者は、目的の受信者に到達する前にトラフィックをモニターし読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="03669-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="03669-148">通信中の各ユーザーは、意図したユーザーとだけ通信していると考えながら、知らずのうちに攻撃者にトラフィックを送信し、攻撃者からトラフィックを受信します。</span><span class="sxs-lookup"><span data-stu-id="03669-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="03669-149">これは、攻撃者が Active Directory ドメイン サービスを変更して信頼するサーバーとして攻撃者のサーバーを追加したり、クライアントがサーバーに接続する際に攻撃者経由で接続するようにドメイン名システム (DNS) を変更できる場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="03669-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="03669-150">Man-in-the-middle 攻撃は、2つのクライアント間のメディアトラフィックでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03669-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="03669-151">ただし、Microsoft Lync Server 2013 では、ポイントツーポイントの音声、ビデオ、およびアプリケーション共有のストリームは、TLS 経由でセッション確立プロトコル (SIP) を使用しているピア間でネゴシエートされる暗号化キーを使用して、SRTP で暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="03669-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="03669-152">グループチャットなどのサーバーは、HTTPS を使って web トラフィックのセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="03669-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="03669-153">RTP 再生攻撃</span><span class="sxs-lookup"><span data-stu-id="03669-153">RTP Replay Attack</span></span>

<span data-ttu-id="03669-p111">*再生攻撃*は、2 者間の有効なメディア伝送が、不正な目的で傍受されて転送される場合に発生します。セキュリティ保護されたシグナリング プロトコルでの接続で使用される SRTP は、受信側が、既に受信した RTP パケットのインデックスを保持して、インデックスに既にリストされているパケットと新しい各パケットを比較できるようにすることで、再生攻撃から伝送を守ります。</span><span class="sxs-lookup"><span data-stu-id="03669-p111">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="03669-156">SPIM</span><span class="sxs-lookup"><span data-stu-id="03669-156">Spim</span></span>

<span data-ttu-id="03669-p112">*SPIM* とは、一方的に送りつけられる営利目的のインスタント メッセージまたはプレゼンス サブスクリプション要求のことです。それ自体はネットワークを侵害するものではありませんが、少なくとも迷惑なものであり、リソースの可用性および生産性を低下させ、結果としてネットワークの侵害を招く可能性があります。SPIM の一例として、ユーザーが要求を送信することで相互に SPIM を送るケースがあります。ユーザーは相互にブロックしてこれを防ぐことができますが、フェデレーションの場合、調整された SPIM 攻撃が確立されると、パートナーのフェデレーションを無効にしない限り、対処が困難になるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="03669-p112">*Spim* is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="03669-161">ウイルスとワーム</span><span class="sxs-lookup"><span data-stu-id="03669-161">Viruses and Worms</span></span>

<span data-ttu-id="03669-p113">*ウイルス*は、同種の追加コード単位の複製を目的としたコード単位です。ウイルスは、有効に機能するためにホスト (ファイル、電子メール、プログラムなど) を必要とします。*ワーム*は、同種の追加コード単位を複製することを意図するコード単位ですが、ホストを必要としません。ウイルスとワームは、クライアント間でファイルを転送しているとき、または他のユーザーから URL が送信されたときに主に出現します。ウイルスがコンピューター上に存在する場合、そのウイルスは、たとえば、無断でユーザー ID を使用してインスタント メッセージを送信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03669-p113">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units. To work, a virus needs a host, such as a file, email, or program. A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host. Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users. If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="03669-167">個人を特定できる情報</span><span class="sxs-lookup"><span data-stu-id="03669-167">Personally Identifiable Information</span></span>

<span data-ttu-id="03669-168">Microsoft Lync Server 2013 は、個人にリンクできる可能性があるパブリックネットワーク経由で情報を開示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03669-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="03669-169">このような情報は、次の 2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="03669-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="03669-170">**拡張プレゼンスデータ**拡張プレゼンスデータとは、フェデレーションパートナーまたは組織内の連絡先へのリンクを共有したり、共有したりすることを選択できる情報です。</span><span class="sxs-lookup"><span data-stu-id="03669-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="03669-171">このデータはオープン インスタント メッセージ (IM) ネットワーク上のユーザーとは共有されません。</span><span class="sxs-lookup"><span data-stu-id="03669-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="03669-172">クライアント ポリシーや他のクライアント設定により、システム管理者に何らかのコントロールを与えることができます。</span><span class="sxs-lookup"><span data-stu-id="03669-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="03669-173">Lync Server 2013 では、ユーザーの連絡先リストに含まれていない Lync ユーザーがユーザーのプレゼンス情報を見ることができないように、個々のユーザーに対して、強化されたプレゼンスプライバシーモードを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="03669-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="03669-174">拡張プレゼンスプライバシーモードでは、Microsoft Office Communicator 2007 および Microsoft Office Communicator 2007 R2 のユーザーがユーザーのプレゼンス情報を見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="03669-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="03669-175">詳細については、「はじめに」のドキュメントで「 [Lync server 2013 のクライアントの新機能](lync-server-2013-what-s-new-for-clients.md)」を参照してください。展開ドキュメントの「 [lync server 2013 でのプレゼンスプライバシーモードの設定](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03669-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="03669-176">**必須データ**必須データは、サーバーまたはクライアントが適切に動作するために必要です。また、クライアントやシステム管理の管理下にはありません。</span><span class="sxs-lookup"><span data-stu-id="03669-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="03669-177">これは、ルーティング、状態管理、およびシグナリングの目的で、サーバーまたはネットワークレベルで必要な情報です。</span><span class="sxs-lookup"><span data-stu-id="03669-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="03669-178">次の表は、パブリック ネットワークで公開されるデータを示しています。</span><span class="sxs-lookup"><span data-stu-id="03669-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="03669-179">拡張プレゼンス データ</span><span class="sxs-lookup"><span data-stu-id="03669-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03669-180">公開されるデータ</span><span class="sxs-lookup"><span data-stu-id="03669-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="03669-181">指定可能な設定</span><span class="sxs-lookup"><span data-stu-id="03669-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03669-182">個人データ</span><span class="sxs-lookup"><span data-stu-id="03669-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="03669-183">名前、役職、会社、電子メール アドレス、タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="03669-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03669-184">電話番号</span><span class="sxs-lookup"><span data-stu-id="03669-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="03669-185">勤務先、携帯、自宅</span><span class="sxs-lookup"><span data-stu-id="03669-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03669-186">予定表情報</span><span class="sxs-lookup"><span data-stu-id="03669-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="03669-187">空き時間、出張の通知、ミーティングの詳細 (予定表にアクセスできるユーザーに公開されます)</span><span class="sxs-lookup"><span data-stu-id="03669-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03669-188">[プレゼンス状態]</span><span class="sxs-lookup"><span data-stu-id="03669-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="03669-189">退席中、連絡可能、取り込み中、応答不可、オフライン</span><span class="sxs-lookup"><span data-stu-id="03669-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="03669-190">必須のデータ</span><span class="sxs-lookup"><span data-stu-id="03669-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03669-191">公開されるデータ</span><span class="sxs-lookup"><span data-stu-id="03669-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="03669-192">情報の例</span><span class="sxs-lookup"><span data-stu-id="03669-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03669-193">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="03669-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="03669-194">コンピューターの実際のアドレスまたは NAT で変換したアドレス</span><span class="sxs-lookup"><span data-stu-id="03669-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03669-195">SIP URI</span><span class="sxs-lookup"><span data-stu-id="03669-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="03669-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="03669-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

