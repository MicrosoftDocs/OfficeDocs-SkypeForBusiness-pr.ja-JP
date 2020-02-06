---
title: DNS SRV レコードの更新
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812775"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="c74c6-103">DNS SRV レコードの更新</span><span class="sxs-lookup"><span data-stu-id="c74c6-103">Update DNS SRV records</span></span>

<span data-ttu-id="c74c6-104">この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c74c6-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="c74c6-105">このトピックでは、Skype for Business Server 2019 に移行した後に、ドメインネームシステム (DNS) レコードを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c74c6-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="c74c6-106">すべてのユーザーが Skype for Business Server 2019 に移動された後、以前のプールまたはディレクターが廃止される前に、すべての SIP ドメインの内部 DNS の DNS SRV レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c74c6-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="c74c6-107">この手順では、内部 DNS に SIP ユーザードメイン用のゾーンが含まれていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c74c6-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="c74c6-108">DNS SRV レコードを構成するには</span><span class="sxs-lookup"><span data-stu-id="c74c6-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="c74c6-109">DNS サーバーで [**スタート**] をクリックし、[**管理ツール**]、[ **dns**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74c6-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="c74c6-110">SIP ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Skype For business Server 2019 がインストールされている SIP ドメインを展開して、 **_tcp**設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="c74c6-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="c74c6-111">右側のウィンドウで **_sipinternaltls**を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c74c6-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="c74c6-112">[**このサービスを提供**しているホスト] で、[Skype For business Server 2019 プール] をポイントするようにホストの FQDN を更新します。</span><span class="sxs-lookup"><span data-stu-id="c74c6-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="c74c6-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74c6-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="c74c6-114">フロントエンドプールまたは Standard Edition サーバーの FQDN が解決できることを確認するには</span><span class="sxs-lookup"><span data-stu-id="c74c6-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="c74c6-115">ドメイン内のクライアントコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c74c6-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="c74c6-116">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74c6-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="c74c6-117">[**開く**] ボックスに cmd と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74c6-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="c74c6-118">コマンドプロンプトに、 _ \<標準エディションサーバー\>の_ _ \<フロントエンドプール\> _または fqdn の nslookup FQDN と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c74c6-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="c74c6-119">FQDN の適切な IP アドレスに解決される返信を受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c74c6-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

