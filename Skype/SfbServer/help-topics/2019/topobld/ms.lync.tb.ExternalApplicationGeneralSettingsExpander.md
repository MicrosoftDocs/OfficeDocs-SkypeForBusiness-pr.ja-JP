---
title: 外部アプリケーションの全般設定の拡張
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 既に定義されている信頼されたアプリケーション サーバーのプロパティを編集するには、これらの指示に従います。
ms.openlocfilehash: b01e48a3d2a003295956df981c4b571a7494be34
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993100"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="cc927-103">外部アプリケーションの全般設定の拡張</span><span class="sxs-lookup"><span data-stu-id="cc927-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="cc927-104">既に定義されている信頼されたアプリケーション サーバーのプロパティを編集するには、これらの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="cc927-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="cc927-105">変更可能な 2 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="cc927-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="cc927-106">全般設定</span><span class="sxs-lookup"><span data-stu-id="cc927-106">General settings</span></span>
    
> <span data-ttu-id="cc927-107">次ホップ設定</span><span class="sxs-lookup"><span data-stu-id="cc927-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="cc927-108">全般設定</span><span class="sxs-lookup"><span data-stu-id="cc927-108">General Settings</span></span>

<span data-ttu-id="cc927-109">信頼されたアプリケーション サーバー プールの現在の完全修飾ドメイン名 (FQDN) を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="cc927-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="cc927-110">プールの FQDN の名前を編集します。</span><span class="sxs-lookup"><span data-stu-id="cc927-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="cc927-111">クライアントの前に新しいエントリのドメイン ネーム システム (DNS) ホスト (A) レコードが存在する必要がありますか、サーバーは、新しいプールの名前に接続できます。</span><span class="sxs-lookup"><span data-stu-id="cc927-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="cc927-112">このプールへの構成データのレプリケーションが必要な場合は、**このプールへの構成データのレプリケーションを有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc927-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="cc927-113">構成データをレプリケートしたくない場合は、チェック マークをオフにします。</span><span class="sxs-lookup"><span data-stu-id="cc927-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="cc927-114">次ホップの設定</span><span class="sxs-lookup"><span data-stu-id="cc927-114">Next Hop Settings</span></span>

<span data-ttu-id="cc927-115">ドロップ ダウン リストから定義済みのエンタープライズ エディションのフロント エンド プールまたは標準的なフロント エンド サーバーのエディションを選択することによって、信頼されたアプリケーション サーバー プールの次ホップのサーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc927-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="cc927-116">ディレクターまたはディレクター プールを選択し、信頼されたアプリケーション サーバーの次のホップの選択が有効な一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="cc927-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="cc927-117">受け入れるし、変更内容を保存して **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc927-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="cc927-118">変更を破棄してプロパティ ページを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc927-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

