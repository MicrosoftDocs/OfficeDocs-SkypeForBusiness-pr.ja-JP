---
title: 外部アプリケーション全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: 既に定義されている信頼できるアプリケーションサーバーのプロパティを編集するには、次の手順を実行します。
ms.openlocfilehash: dffeb52ab1633a936a73cb2270a204d26ccf1056
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702172"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="aa686-103">外部アプリケーション全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="aa686-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="aa686-104">既に定義されている信頼できるアプリケーションサーバーのプロパティを編集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa686-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="aa686-105">変更できるセクションは2つあります。</span><span class="sxs-lookup"><span data-stu-id="aa686-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="aa686-106">全般設定</span><span class="sxs-lookup"><span data-stu-id="aa686-106">General settings</span></span>
> 
> <span data-ttu-id="aa686-107">次ホップ設定</span><span class="sxs-lookup"><span data-stu-id="aa686-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="aa686-108">全般設定</span><span class="sxs-lookup"><span data-stu-id="aa686-108">General Settings</span></span>

<span data-ttu-id="aa686-109">信頼されているアプリケーションサーバープールの現在の完全修飾ドメイン名 (FQDN) を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="aa686-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="aa686-110">プールの FQDN の名前を編集します。</span><span class="sxs-lookup"><span data-stu-id="aa686-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="aa686-111">クライアントまたはサーバーが新しいプール名に接続できるようにするには、新しいエントリにドメインネームシステム (DNS) レコードが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa686-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="aa686-112">このプールに構成データを複製する必要がある場合は、[**このプールへの構成データのレプリケーションを有効**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa686-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="aa686-113">構成データを複製しない場合は、チェックマークをオフにします。</span><span class="sxs-lookup"><span data-stu-id="aa686-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="aa686-114">次ホップの設定</span><span class="sxs-lookup"><span data-stu-id="aa686-114">Next Hop Settings</span></span>

<span data-ttu-id="aa686-115">定義済みの Enterprise Edition のフロントエンドプールまたは標準エディションのフロントエンドサーバーをドロップダウンリストから選択して、信頼できるアプリケーションサーバープールの次ホップサーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="aa686-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="aa686-116">ディレクターまたはディレクタープールが、信頼できるアプリケーションサーバーの次ホップの有効な選択ではないため、一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="aa686-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="aa686-117">[ **OK]** をクリックして、変更を承諾して保存します。</span><span class="sxs-lookup"><span data-stu-id="aa686-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="aa686-118">変更を破棄してプロパティ ページを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa686-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

