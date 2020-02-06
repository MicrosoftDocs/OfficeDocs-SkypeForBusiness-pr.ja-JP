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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: 入力-CcUpdate コマンドレットは、Skype for Business Cloud Connector Edition host server をメンテナンスモードにして、更新プロセスを準備します。 アプライアンスは直ちにすべてのサービスを停止して、進行中の通話を終了し、新しい通話を拒否します。
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802177"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="e9144-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e9144-104">Enter-CcUpdate</span></span>

<span data-ttu-id="e9144-105">入力-CcUpdate コマンドレットは、Skype for Business Cloud Connector Edition host server をメンテナンスモードにして、更新プロセスを準備します。</span><span class="sxs-lookup"><span data-stu-id="e9144-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="e9144-106">アプライアンスは直ちにすべてのサービスを停止して、進行中の通話を終了し、新しい通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="e9144-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="e9144-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9144-107">Parameters</span></span>

<span data-ttu-id="e9144-108">なし</span><span class="sxs-lookup"><span data-stu-id="e9144-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e9144-109">例</span><span class="sxs-lookup"><span data-stu-id="e9144-109">Examples</span></span>
<span data-ttu-id="e9144-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e9144-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e9144-111">例 1</span><span class="sxs-lookup"><span data-stu-id="e9144-111">Example 1</span></span>

<span data-ttu-id="e9144-112">次の例では、アプライアンスをメンテナンス モードに入れて更新プロセスに備えています。</span><span class="sxs-lookup"><span data-stu-id="e9144-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="e9144-113">解説</span><span class="sxs-lookup"><span data-stu-id="e9144-113">Detailed Description</span></span>
<span data-ttu-id="e9144-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e9144-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e9144-115">入力-CcUpdate コマンドレットは、現在進行中の通話を終了するすべてのサービスを直ちに停止します。このアプライアンスは、他の運用アプライアンスに転送される新しい通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="e9144-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="e9144-116">更新を準備しているアプライアンスからの通話を処理するために、残りの本番アプライアンスに十分な容量があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9144-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="e9144-p104">お使いのアプライアンスで自動更新が有効になっている場合に、マイクロソフトが重要な修正プログラムをリリースするときなどで、メンテナンス モードは役に立ちます。メンテナンス モードは、自動更新をオフにすることを決めた上で、一貫して手動での更新を実行するという場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e9144-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="e9144-119">更新プログラムをインストールした後、終了-CcUpdate コマンドレットを実行して、アプライアンスを運用モードに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="e9144-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9144-120">クラウドコネクタのアプライアンスを手動で更新する場合は、Microsoft が次のバージョンをリリースしてから60日以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9144-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="e9144-121">Microsoft は、新しいバージョンがリリースされてから60日間、以前リリースされたクラウドコネクタのバージョンをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e9144-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="e9144-122">入力の種類</span><span class="sxs-lookup"><span data-stu-id="e9144-122">Input Types</span></span>
<span data-ttu-id="e9144-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9144-123"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e9144-p106">なし。Enter-CCUpdate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="e9144-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e9144-126">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="e9144-126">Return Types</span></span>
<span data-ttu-id="e9144-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9144-127"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e9144-128">なし</span><span class="sxs-lookup"><span data-stu-id="e9144-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e9144-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9144-129">See also</span></span>
<span data-ttu-id="e9144-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9144-130"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e9144-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e9144-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

