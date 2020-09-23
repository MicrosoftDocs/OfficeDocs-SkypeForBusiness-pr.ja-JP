---
title: 外部アプリケーション全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 既に定義されている信頼済みアプリケーション サーバーのプロパティを編集するには、以下の操作を行います。
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218138"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="ea7bb-103">外部アプリケーション全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="ea7bb-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="ea7bb-104">既に定義されている信頼済みアプリケーション サーバーのプロパティを編集するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ea7bb-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="ea7bb-105">更新できるセクションは以下の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="ea7bb-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="ea7bb-106">全般設定</span><span class="sxs-lookup"><span data-stu-id="ea7bb-106">General settings</span></span>
> 
> <span data-ttu-id="ea7bb-107">次ホップ設定</span><span class="sxs-lookup"><span data-stu-id="ea7bb-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="ea7bb-108">全般設定</span><span class="sxs-lookup"><span data-stu-id="ea7bb-108">General Settings</span></span>

<span data-ttu-id="ea7bb-p101">信頼されたアプリケーション サーバー プールの現在の完全修飾ドメイン名 (FQDN) を変更できます。プールの FQDN の名前を編集します。クライアントまたはサーバーが新しいプール名に接続できるようにするには、新しいエントリのドメイン ネーム システム (DNS) ホスト (A) のレコードが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea7bb-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="ea7bb-p102">このプールへの構成データのレプリケーションが必要な場合は、[**このプールへの構成データのレプリケーションを有効にする**] をオンにします。構成データをレプリケーションしない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ea7bb-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="ea7bb-114">次ホップ設定</span><span class="sxs-lookup"><span data-stu-id="ea7bb-114">Next Hop Settings</span></span>

<span data-ttu-id="ea7bb-115">信頼済みアプリケーションサーバープールの次ホップサーバーを指定するには、定義済みの Enterprise Edition フロントエンドプールまたは Standard Edition フロントエンドサーバーをドロップダウンリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="ea7bb-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="ea7bb-116">ディレクターまたはディレクター プールは、信頼されたアプリケーション サーバーの次ホップとしては有効な選択肢ではないため、リストに表示されません。</span><span class="sxs-lookup"><span data-stu-id="ea7bb-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="ea7bb-117">[ **OK]** をクリックして変更を受け入れ、保存します。</span><span class="sxs-lookup"><span data-stu-id="ea7bb-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="ea7bb-118">変更を破棄してプロパティ ページを終了するには、**[キャンセル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea7bb-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

