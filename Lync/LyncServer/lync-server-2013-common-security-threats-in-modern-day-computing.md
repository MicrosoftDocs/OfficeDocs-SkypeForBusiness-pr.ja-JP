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
ms.openlocfilehash: b9869f3c903aa7b16529ed72c499a1cb41254634
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="e3f06-102">最近のコンピューティングでの一般的なセキュリティの脅威</span><span class="sxs-lookup"><span data-stu-id="e3f06-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3f06-103">_**トピックの最終更新日:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="e3f06-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="e3f06-104">Lync Server 2013 はエンタープライズクラスの通信システムであるため、インフラストラクチャと通信に影響する可能性のある一般的なセキュリティ攻撃に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="e3f06-105">危殆化鍵による攻撃</span><span class="sxs-lookup"><span data-stu-id="e3f06-105">Compromised-Key Attack</span></span>

<span data-ttu-id="e3f06-106">キーは、機密情報の暗号化、復号化、または検証に使用される秘密のコードまたは番号です。</span><span class="sxs-lookup"><span data-stu-id="e3f06-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="e3f06-107">公開キー基盤 (PKI) では、次の2つの重要なキーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="e3f06-108">各証明書所有者が持つ秘密キー</span><span class="sxs-lookup"><span data-stu-id="e3f06-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="e3f06-109">通信パートナーによって id とセッションキーが正常に交換された後に使用されるセッションキー</span><span class="sxs-lookup"><span data-stu-id="e3f06-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="e3f06-110">侵害されたキー攻撃は、攻撃者が秘密キーまたはセッションキーを決定したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="e3f06-111">攻撃者がキーを決定して成功した場合、攻撃者はそのキーを使用して、送信者に関する情報を持たずに暗号化されたデータを解読できます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="e3f06-112">Lync Server 2013 は、Windows Server オペレーティングシステムの PKI 機能を使用して、トランスポート層セキュリティ (TLS) 接続の暗号化に使用されるキーデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="e3f06-113">メディアの暗号化に使用されるキーは、TLS 接続を介して交換されます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="e3f06-114">ネットワークのサービス拒否攻撃</span><span class="sxs-lookup"><span data-stu-id="e3f06-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="e3f06-115">*サービス拒否攻撃*は、攻撃者が通常のネットワーク使用を妨げ、有効なユーザーによって機能しない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="e3f06-116">これは、攻撃者が正規の要求によってサービスをフラッディングするときに実行されます。正当なユーザーによるサービスの使用を過負荷にします。</span><span class="sxs-lookup"><span data-stu-id="e3f06-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="e3f06-117">サービス拒否攻撃を使用して、攻撃者は次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="e3f06-118">攻撃対象のネットワークで実行されているアプリケーションまたはサービスに対して無効なデータを送信して、そのようなアプリケーションまたはサービスが正常に機能するのを妨害する。</span><span class="sxs-lookup"><span data-stu-id="e3f06-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="e3f06-119">大量のトラフィックを送信してシステムを過負荷状態にして、適正な要求に対するシステムの応答を停止または低速化する。</span><span class="sxs-lookup"><span data-stu-id="e3f06-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="e3f06-120">攻撃の証拠を隠蔽する。</span><span class="sxs-lookup"><span data-stu-id="e3f06-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="e3f06-121">ユーザーがネットワーク リソースにアクセスできないようにする。</span><span class="sxs-lookup"><span data-stu-id="e3f06-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="e3f06-122">盗聴 (スニッフィング、スヌーピング)</span><span class="sxs-lookup"><span data-stu-id="e3f06-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="e3f06-123">*盗聴*は、攻撃者がネットワーク内のデータパスにアクセスし、トラフィックを監視および読み取りできる場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="e3f06-124">これは、*スニッフィング*または*スヌーピング*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="e3f06-125">トラフィックがプレーン テキストの場合、攻撃者は、ネットワークのパスにアクセスしたときにトラフィックを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="e3f06-126">例としては、データ パス上のルーターを制御することによって実行される攻撃があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="e3f06-127">Microsoft Lync Server 2013 内のトラフィックに対する既定の推奨事項と設定は、信頼されたサーバーとクライアントからサーバーへの TLS 間で相互 TLS (MTLS) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="e3f06-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="e3f06-128">この保護措置により、特定の会話が発生した期間内に、攻撃が非常に困難または不可能になることがあります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="e3f06-129">TLS はすべての関係者を認証し、すべてのトラフィックを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="e3f06-130">これにより盗聴は防止されませんが、攻撃者は暗号化が解除されていない限りトラフィックを読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="e3f06-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="e3f06-131">中継 NAT (TURN) プロトコルを使用してトラバースすることで、トラフィックの暗号化が義務付けられず、送信する情報がメッセージの整合性によって保護されます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="e3f06-132">これは盗聴に対して開かれていますが、送信する情報 (つまり IP アドレスとポート) は、パケットの送信元と送信先のアドレスを参照するだけで、直接抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="e3f06-133">音声ビデオエッジサービスを使用すると、メッセージのメッセージの整合性をチェックすることによって、クリアテキストで送信されることがないいくつかのアイテムから派生したキーを使用して、データが有効であることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="e3f06-134">セキュアリアルタイムプロトコル (SRTP) が使用されている場合、メディアトラフィックも暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="e3f06-135">Id のスプーフィング (IP アドレスのスプーフィング)</span><span class="sxs-lookup"><span data-stu-id="e3f06-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="e3f06-136">*スプーフィング*は、攻撃者が許可されずに、ネットワーク、コンピューター、またはネットワークコンポーネントの IP アドレスを決定し、使用した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="e3f06-137">攻撃に成功した場合、攻撃者は、通常その IP アドレスで識別されるエンティティであるかのように振る舞うことができます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="e3f06-138">Microsoft Lync Server 2013 のコンテキストでは、管理者が次の両方の操作を実行した場合にのみ、この状況が発生します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="e3f06-139">伝送制御プロトコル (TCP) のみをサポートする接続を構成した (TCP 接続は暗号化されないため、推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="e3f06-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="e3f06-140">このような接続の IP アドレスを信頼されたホストとしてマークした。</span><span class="sxs-lookup"><span data-stu-id="e3f06-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="e3f06-141">これは、トランスポート層セキュリティ (TLS) 接続の場合の問題であり、TLS はすべての関係者を認証し、すべてのトラフィックを暗号化することになります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="e3f06-142">TLS を使用すると、攻撃者が特定の接続 (たとえば、相互 TLS 接続) で IP アドレススプーフィングを実行するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="e3f06-143">しかし、ハッカーは Lync Server 2013 が使用する DNS サーバーのアドレスを偽装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="e3f06-144">ただし、Lync での認証は証明書を使用して実行されるため、攻撃者は通信でいずれかの当事者のスプーフィングを行うために必要な証明書を持っていません。</span><span class="sxs-lookup"><span data-stu-id="e3f06-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="e3f06-145">中間にある攻撃</span><span class="sxs-lookup"><span data-stu-id="e3f06-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="e3f06-146">中間攻撃は、攻撃者が2人の通信ユーザーを知らなくても、攻撃者のコンピューターを経由して2人のユーザー間の通信を再ルーティングするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="e3f06-147">攻撃者は、目的の受信者に送信する前にトラフィックを監視して読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="e3f06-148">通信中の各ユーザーは、意図したユーザーとのみ通信していることを考慮しつつ、攻撃者からのトラフィックを知らずに送信して受信します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="e3f06-149">これは、攻撃者が Active Directory ドメインサービスを変更して、信頼されたサーバーとしてサーバーを追加するか、またはドメインネームシステム (DNS) を変更することによって、攻撃者がサーバーに接続できるようにクライアントを取得することによって発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="e3f06-150">中央攻撃は、2つのクライアント間のメディアトラフィックでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="e3f06-151">ただし、Microsoft Lync Server 2013 のポイントツーポイントの音声、ビデオ、およびアプリケーション共有では、セッション開始プロトコル (SIP) を TLS 経由で使用しているピア間でネゴシエートされる暗号化キーを使用して、ストリームが SRTP で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="e3f06-152">グループチャットなどのサーバーは、HTTPS を使用して web トラフィックのセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="e3f06-153">RTP 再生攻撃</span><span class="sxs-lookup"><span data-stu-id="e3f06-153">RTP Replay Attack</span></span>

<span data-ttu-id="e3f06-154">*再生攻撃*は、2つの当事者間の有効なメディア転送が傍受され、悪意のある目的のために再送信されるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="e3f06-155">セキュリティ保護されたシグナリング プロトコルでの接続で使用される SRTP は、受信側が、既に受信した RTP パケットのインデックスを保持して、インデックスに既にリストされているパケットと新しい各パケットを比較できるようにすることで、再生攻撃から伝送を守ります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="e3f06-156">Spim</span><span class="sxs-lookup"><span data-stu-id="e3f06-156">Spim</span></span>

<span data-ttu-id="e3f06-157">*Spim*は、未承諾の商用インスタントメッセージまたはプレゼンスサブスクリプション要求です。</span><span class="sxs-lookup"><span data-stu-id="e3f06-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="e3f06-158">それ自体はネットワークを侵害するものではありませんが、少なくとも迷惑なものであり、リソースの可用性および生産性を低下させ、結果としてネットワークの侵害を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="e3f06-159">SPIM の一例として、ユーザーが要求を送信することで相互に SPIM を送るケースがあります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="e3f06-160">ユーザーは相互にブロックしてこれを防ぐことができますが、フェデレーションの場合、調整された SPIM 攻撃が確立されると、パートナーのフェデレーションを無効にしない限り、対処が困難になるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="e3f06-161">ウイルスとワーム</span><span class="sxs-lookup"><span data-stu-id="e3f06-161">Viruses and Worms</span></span>

<span data-ttu-id="e3f06-162">*ウイルス*は、同様の追加のコード単位を再現することを目的とするコードの単位です。</span><span class="sxs-lookup"><span data-stu-id="e3f06-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="e3f06-163">ウイルスは、有効に機能するためにホスト (ファイル、電子メール、プログラムなど) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="e3f06-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="e3f06-164">*ワーム*とは、類似した追加のコード単位を再現することを目的とするコードの単位ですが、ホストを必要としません。</span><span class="sxs-lookup"><span data-stu-id="e3f06-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="e3f06-165">ウイルスとワームは、クライアント間でファイルを転送しているとき、または他のユーザーから URL が送信されたときに主に出現します。</span><span class="sxs-lookup"><span data-stu-id="e3f06-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="e3f06-166">ウイルスがコンピューター上に存在する場合、そのウイルスは、たとえば、無断でユーザー ID を使用してインスタント メッセージを送信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="e3f06-167">個人を特定できる情報</span><span class="sxs-lookup"><span data-stu-id="e3f06-167">Personally Identifiable Information</span></span>

<span data-ttu-id="e3f06-168">Microsoft Lync Server 2013 は、個人にリンクされている可能性があるパブリックネットワーク上で情報を公開する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="e3f06-169">このような情報は、次の 2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="e3f06-170">**拡張プレゼンスデータ**拡張プレゼンスデータとは、ユーザーがフェデレーションパートナーへのリンクまたは組織内の連絡先との間で共有したり共有したりすることができないようにするための情報です。</span><span class="sxs-lookup"><span data-stu-id="e3f06-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="e3f06-171">このデータは、パブリック IM ネットワーク上のユーザーとは共有されません。</span><span class="sxs-lookup"><span data-stu-id="e3f06-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="e3f06-172">クライアントポリシーおよびその他のクライアント構成は、システム管理者によって制御されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e3f06-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="e3f06-173">Lync Server 2013 では、ユーザーの連絡先リストに含まれていない Lync ユーザーがユーザーのプレゼンス情報を表示できないように、個々のユーザーに対して拡張プレゼンスプライバシーモードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e3f06-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="e3f06-174">拡張プレゼンスプライバシーモードでは、Microsoft Office Communicator 2007 および Microsoft Office Communicator 2007 R2 のユーザーがユーザーのプレゼンス情報を表示できなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="e3f06-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="e3f06-175">詳細については、「展開」のドキュメントの「[はじめに] のドキュメントと「[拡張プレゼンスのプライバシー2013モードの構成](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)」の「 [lync server 2013 の新しいクライアントの新機能](lync-server-2013-what-s-new-for-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f06-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="e3f06-176">**必須のデータ**サーバーまたはクライアントの適切な操作に必須のデータが必要であり、クライアントまたはシステム管理の制御下にありません。</span><span class="sxs-lookup"><span data-stu-id="e3f06-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="e3f06-177">これは、ルーティング、状態の保守、および信号を目的として、サーバーまたはネットワークレベルで必要な情報です。</span><span class="sxs-lookup"><span data-stu-id="e3f06-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="e3f06-178">次の表は、パブリックネットワークで公開されるデータを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3f06-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="e3f06-179">拡張プレゼンス データ</span><span class="sxs-lookup"><span data-stu-id="e3f06-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3f06-180">公開データ</span><span class="sxs-lookup"><span data-stu-id="e3f06-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="e3f06-181">使用可能な設定</span><span class="sxs-lookup"><span data-stu-id="e3f06-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3f06-182">個人データ</span><span class="sxs-lookup"><span data-stu-id="e3f06-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="e3f06-183">名前、役職、会社、電子メールアドレス、タイムゾーン</span><span class="sxs-lookup"><span data-stu-id="e3f06-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f06-184">電話番号</span><span class="sxs-lookup"><span data-stu-id="e3f06-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="e3f06-185">勤務先、携帯、自宅</span><span class="sxs-lookup"><span data-stu-id="e3f06-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3f06-186">予定表情報</span><span class="sxs-lookup"><span data-stu-id="e3f06-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="e3f06-187">空き時間情報、不在時の通知、会議の詳細 (予定表へのアクセス権を持つユーザーに対して)</span><span class="sxs-lookup"><span data-stu-id="e3f06-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f06-188">プレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="e3f06-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="e3f06-189">退席中、連絡可能、取り込み中、応答不可、オフライン</span><span class="sxs-lookup"><span data-stu-id="e3f06-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="e3f06-190">必須のデータ</span><span class="sxs-lookup"><span data-stu-id="e3f06-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3f06-191">公開データ</span><span class="sxs-lookup"><span data-stu-id="e3f06-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="e3f06-192">情報の例</span><span class="sxs-lookup"><span data-stu-id="e3f06-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3f06-193">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e3f06-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="e3f06-194">コンピューターの実際のアドレスまたは NAT で変換したアドレス</span><span class="sxs-lookup"><span data-stu-id="e3f06-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3f06-195">SIP URI</span><span class="sxs-lookup"><span data-stu-id="e3f06-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e3f06-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e3f06-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

