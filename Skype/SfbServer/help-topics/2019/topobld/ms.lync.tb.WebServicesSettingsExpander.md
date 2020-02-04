---
title: Web サービス設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジビルダーでは、内部と外部の両方の web サービスで使用されるポート設定を変更できます。 さらに、ドメインネームシステム (DNS) 負荷分散を展開している場合は、トポロジビルダーを使用して、そのプールのすべてのサーバーの物理 IP アドレスに解決されるプールの完全修飾ドメイン名 (FQDN) を構成することもできます。
ms.openlocfilehash: fddcaa00de9b8a8d74e209790b429280901b037c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701342"
---
# <a name="web-services-settings-expander"></a><span data-ttu-id="9b0cb-104">Web サービス設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="9b0cb-104">Web Services Settings Expander</span></span>
 
<span data-ttu-id="9b0cb-105">トポロジビルダーでは、内部と外部の両方の web サービスで使用されるポート設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-105">From within Topology Builder, you can modify the port settings used for both your internal and external web services.</span></span> <span data-ttu-id="9b0cb-106">さらに、ドメインネームシステム (DNS) 負荷分散を展開している場合は、トポロジビルダーを使用して、そのプールのすべてのサーバーの物理 IP アドレスに解決されるプールの完全修飾ドメイン名 (FQDN) を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-106">In addition, and if you are deploying Domain Name System (DNS) load balancing, you can use Topology Builder to configure the fully qualified domain name (FQDN) of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span>
  
### <a name="editing-web-services-settings"></a><span data-ttu-id="9b0cb-107">Web サービス設定の編集</span><span class="sxs-lookup"><span data-stu-id="9b0cb-107">Editing Web Services Settings</span></span>

1. <span data-ttu-id="9b0cb-108">該当する Standard Edition フロントエンド サーバーまたは Enterprise Edition フロントエンド プールを選択し、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-108">Select the appropriate Standard Edition Front End Server or the appropriate Enterprise Edition Front End Pool, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="9b0cb-109">[**プロパティの編集**] ダイアログ ボックスで、[**Web サービス**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-109">In the **Edit Properties** dialog box, click the **Web services** tab.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="9b0cb-110">フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-110">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="9b0cb-111">たとえば、フロントエンドサーバーの外部 Web サービス FQDN を**pool01.contoso.com**として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して**pool01.contoso.com**を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-111">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="9b0cb-112">ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-112">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="9b0cb-113">自動定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-113">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
3. <span data-ttu-id="9b0cb-114">Enterprise Edition プールのプロパティを編集する場合は、[**FQDN の上書き**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-114">If you are editing the properties of an Enterprise Edition pool, you have the option to select **Override FQDN**.</span></span> <span data-ttu-id="9b0cb-115">このオプションは、ドメイン ネーム システム (DNS) 負荷分散を使用する場合にのみ選択してください。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-115">This option should be selected only if you are using Domain Name System (DNS) load balancing.</span></span> <span data-ttu-id="9b0cb-116">DNS 負荷分散を使用する場合は、[**FQDN の上書き**] を選択してから、テキスト ボックスにプール内のすべてのサーバーの物理 IP アドレスに解決するそのプールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-116">If you are using DNS load balancing, select **Override FQDN** and then, in the text box, type the FQDN of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span> <span data-ttu-id="9b0cb-117">DNS 負荷分散を使用しない場合、および [**FQDN の上書き**] を選択しない場合は、内部 Web サービスの FQDN を変更できません。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-117">If you are not using DNS load balancing, and if you do not select **Override FQDN**, you cannot change the Internal web services FQDN.</span></span> <span data-ttu-id="9b0cb-118">内部 web サービス FQDN は、内部ユーザーが Skype for Business Server に接続するために使用する URL です。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-118">The Internal web services FQDN is the URL used by internal users to connect to Skype for Business Server.</span></span>
    
4. <span data-ttu-id="9b0cb-p105">オプションとして、[**リッスン ポート**] および [**公開ポート**] に、新しい HTTP、HTTPS、または HTTP と HTTPS の値を入力します。リッスン ポートは、着信側のセッション開始プロトコル (SIP) トラフィックをリッスンするためにインターネット インフォメーション サービス (IIS) で使用されるポートです。公開ポートは、ロード バランサーまたはリバース プロキシ サーバーで構成されるポートで、やはり着信 SIP トラフィックをリッスンするために使用されます。既定では、HTTP リッスン ポートと HTTP 公開ポートの両方がポート 80 に設定されており、対応する HTTPS ポートは両方とも 443 に設定されます。2 つの HTTP 公開ポートの既定値は 8080 で、対応する HTTPS ポートは 4443 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-p105">Optionally, enter new HTTP, HTTPS, or HTTP and HTTPS values for the **Listening ports** and the **Published ports**. Listening ports are the ports used by Internet Information Services (IIS) to listen for incoming Session Initiation Protocol (SIP) traffic; published ports are ports configured on a load balancer or reverse proxy server and are also used to listen for incoming SIP traffic. By default, both the HTTP listening port and the HTTP published port are set to port 80; the corresponding HTTPS ports are both set to 443. The default value for the two HTTP published ports is 8080 and the corresponding HTTPS ports are set to 4443.</span></span>
    
5. <span data-ttu-id="9b0cb-123">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-123">Click **OK**.</span></span>
    
<span data-ttu-id="9b0cb-124">内部 FQDN またはいずれかのリッスン ポートの割り当てを変更する場合は、変更を有効にするために、プール内のすべてのサーバーでローカル セットアップを再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b0cb-124">If you modify either the internal FQDN or any of the listening port assignments, you must local setup again on all the servers in the pool in order to have those changes take effect.</span></span>
  

