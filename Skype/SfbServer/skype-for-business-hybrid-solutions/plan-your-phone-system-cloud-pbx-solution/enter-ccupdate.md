---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: 入力-CcUpdate コマンドレットは、Skype for Business Cloud Connector Edition host server をメンテナンスモードにして、更新プロセスを準備します。 このアプライアンスは、すべての既存の通話が完了しますが、新しい通話は拒否されます。
ms.openlocfilehash: be57261b35cf5b5e6e8118c2a751eee1c8b5f2a7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287441"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="3b80b-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="3b80b-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="3b80b-105">入力-CcUpdate コマンドレットは、Skype for Business Cloud Connector Edition host server をメンテナンスモードにして、更新プロセスを準備します。</span><span class="sxs-lookup"><span data-stu-id="3b80b-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="3b80b-106">このアプライアンスは「放電」されています。つまり、すべての既存の通話は完了しますが、新しい通話は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="3b80b-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="3b80b-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b80b-107">Parameters</span></span>

<span data-ttu-id="3b80b-108">なし</span><span class="sxs-lookup"><span data-stu-id="3b80b-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3b80b-109">例</span><span class="sxs-lookup"><span data-stu-id="3b80b-109">Examples</span></span>
<span data-ttu-id="3b80b-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3b80b-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="3b80b-111">例 1</span><span class="sxs-lookup"><span data-stu-id="3b80b-111">Example 1</span></span>

<span data-ttu-id="3b80b-112">次の例では、アプライアンスをメンテナンス モードに入れて更新プロセスに備えています。</span><span class="sxs-lookup"><span data-stu-id="3b80b-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="3b80b-113">解説</span><span class="sxs-lookup"><span data-stu-id="3b80b-113">Detailed Description</span></span>
<span data-ttu-id="3b80b-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3b80b-114"></span></span>

<span data-ttu-id="3b80b-115">入力-CcUpdate コマンドレットは、現在進行中の通話を終了するすべてのサービスを直ちに停止します。このアプライアンスは、他の運用アプライアンスに転送される新しい通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="3b80b-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="3b80b-116">更新を準備しているアプライアンスからの通話を処理するために、残りの本番アプライアンスに十分な容量があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b80b-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="3b80b-p104">お使いのアプライアンスで自動更新が有効になっている場合に、マイクロソフトが重要な修正プログラムをリリースするときなどで、メンテナンス モードは役に立ちます。メンテナンス モードは、自動更新をオフにすることを決めた上で、一貫して手動での更新を実行するという場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b80b-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="3b80b-119">更新プログラムをインストールした後、終了-CcUpdate コマンドレットを実行して、アプライアンスを運用モードに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="3b80b-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b80b-120">クラウドコネクタのアプライアンスを手動で更新する場合は、Microsoft が次のバージョンをリリースしてから60日以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b80b-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="3b80b-121">Microsoft は、新しいバージョンがリリースされてから60日間、以前リリースされたクラウドコネクタのバージョンをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3b80b-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="3b80b-122">入力の種類</span><span class="sxs-lookup"><span data-stu-id="3b80b-122">Input Types</span></span>
<span data-ttu-id="3b80b-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b80b-123"></span></span>

<span data-ttu-id="3b80b-p106">なし。Enter-CCUpdate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="3b80b-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3b80b-126">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="3b80b-126">Return Types</span></span>
<span data-ttu-id="3b80b-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b80b-127"></span></span>

<span data-ttu-id="3b80b-128">なし</span><span class="sxs-lookup"><span data-stu-id="3b80b-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3b80b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b80b-129">See also</span></span>
<span data-ttu-id="3b80b-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b80b-130"></span></span>

[<span data-ttu-id="3b80b-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="3b80b-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

