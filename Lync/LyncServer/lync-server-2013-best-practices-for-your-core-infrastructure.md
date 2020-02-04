---
title: 'Lync Server 2013: コアインフラストラクチャのベストプラクティス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c6a8663bfae2411926fe08a497a5004def051ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="fcc08-102">Lync Server 2013 のコアインフラストラクチャのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="fcc08-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcc08-103">_**最終更新日:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="fcc08-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="fcc08-104">システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段をすでに講じていることでしょう。</span><span class="sxs-lookup"><span data-stu-id="fcc08-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="fcc08-105">この方法では、Microsoft Lync Server 2013 インフラストラクチャだけでなく、ネットワーク全体も利用できます。</span><span class="sxs-lookup"><span data-stu-id="fcc08-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="fcc08-106">これらのプラクティスを実装していない場合は、Lync Server 2013 を展開する前に、この手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fcc08-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="fcc08-107">Lync Server 2013 の展開で、ダウンタイムが発生する可能性のある偶発的または明確の危害からサーバーを保護するために、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcc08-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="fcc08-108">各サーバーに、常に最新のセキュリティ更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="fcc08-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="fcc08-109">マイクロソフト テクニカル セキュリティ情報通知を購読すると、マイクロソフト製品に関するセキュリティ速報を受信できます。</span><span class="sxs-lookup"><span data-stu-id="fcc08-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="fcc08-110">登録するには、の Microsoft テクニカルセキュリティ通知 web サイト[http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcc08-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="fcc08-111">アクセス権が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcc08-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="fcc08-p103">物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="fcc08-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="fcc08-116">Lync Server 2013 をインストールするコンピューターには必要ない Windows Server オペレーティングシステムサービスを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fcc08-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="fcc08-117">サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fcc08-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="fcc08-118">サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="fcc08-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="fcc08-119">DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcc08-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

