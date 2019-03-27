---
title: 外部アプリケーション全般設定エキスパンダー
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 既に定義されている信頼されたアプリケーション サーバーのプロパティを編集するには、これらの指示に従います。
ms.openlocfilehash: a0b25ad3d7570ecb64444821fb0b49b9c65b8e02
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884565"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="e8a29-103">外部アプリケーション全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="e8a29-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="e8a29-104">既に定義されている信頼されたアプリケーション サーバーのプロパティを編集するには、これらの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e8a29-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="e8a29-105">変更可能な 2 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="e8a29-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="e8a29-106">全般設定</span><span class="sxs-lookup"><span data-stu-id="e8a29-106">General settings</span></span>
> 
> <span data-ttu-id="e8a29-107">次ホップ設定</span><span class="sxs-lookup"><span data-stu-id="e8a29-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="e8a29-108">全般設定</span><span class="sxs-lookup"><span data-stu-id="e8a29-108">General Settings</span></span>

<span data-ttu-id="e8a29-109">信頼されたアプリケーション サーバー プールの現在の完全修飾ドメイン名 (FQDN) を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e8a29-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="e8a29-110">プールの FQDN の名前を編集します。</span><span class="sxs-lookup"><span data-stu-id="e8a29-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="e8a29-111">クライアントの前に新しいエントリのドメイン ネーム システム (DNS) ホスト (A) レコードが存在する必要がありますか、サーバーは、新しいプールの名前に接続できます。</span><span class="sxs-lookup"><span data-stu-id="e8a29-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="e8a29-112">このプールへの構成データのレプリケーションが必要な場合は、**このプールへの構成データのレプリケーションを有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8a29-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="e8a29-113">構成データをレプリケートしたくない場合は、チェック マークをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e8a29-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="e8a29-114">次ホップの設定</span><span class="sxs-lookup"><span data-stu-id="e8a29-114">Next Hop Settings</span></span>

<span data-ttu-id="e8a29-115">ドロップ ダウン リストから定義済みのエンタープライズ エディションのフロント エンド プールまたは標準的なフロント エンド サーバーのエディションを選択することによって、信頼されたアプリケーション サーバー プールの次ホップのサーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8a29-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="e8a29-116">ディレクターまたはディレクター プールを選択し、信頼されたアプリケーション サーバーの次のホップの選択が有効な一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="e8a29-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="e8a29-117">受け入れるし、変更内容を保存して **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8a29-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="e8a29-118">変更を破棄してプロパティ ページを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8a29-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

