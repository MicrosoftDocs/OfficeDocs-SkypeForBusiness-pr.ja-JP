---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter CcUpdate コマンドレットでは、メンテナンス モードで配置することによって更新プロセスにホスト サーバーでビジネス クラウド コネクタ版 Skype を準備します。 アプライアンスの isdrained-は、既存のすべての呼び出しは完了しますが、新しい呼び出しは拒否されます。
ms.openlocfilehash: 45972058cd9263330b6a4c0a68a5a1b800a85d9d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882580"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="50236-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="50236-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="50236-105">Enter CcUpdate コマンドレットでは、メンテナンス モードで配置することによって更新プロセスにホスト サーバーでビジネス クラウド コネクタ版 Skype を準備します。</span><span class="sxs-lookup"><span data-stu-id="50236-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="50236-106">アプライアンスは、「放電」つまり、既存すべて呼び出しは完了しますが、新しい呼び出しは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="50236-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="50236-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50236-107">Parameters</span></span>

<span data-ttu-id="50236-108">なし</span><span class="sxs-lookup"><span data-stu-id="50236-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="50236-109">例</span><span class="sxs-lookup"><span data-stu-id="50236-109">Examples</span></span>
<span data-ttu-id="50236-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="50236-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="50236-111">例 1</span><span class="sxs-lookup"><span data-stu-id="50236-111">Example 1</span></span>

<span data-ttu-id="50236-112">次の例では、アプライアンスをメンテナンス モードに入れて更新プロセスに備えています。</span><span class="sxs-lookup"><span data-stu-id="50236-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="50236-113">解説</span><span class="sxs-lookup"><span data-stu-id="50236-113">Detailed Description</span></span>
<span data-ttu-id="50236-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="50236-114"></span></span>

<span data-ttu-id="50236-115">入力 CcUpdate コマンドレットは、継続的な呼び出しを終了するすべてのサービスを直ちに停止し、アプライアンスは、他の生産のアプライアンスに転送されるすべての新しい呼び出しを拒否します。</span><span class="sxs-lookup"><span data-stu-id="50236-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="50236-116">生産の残りのアプライアンスに更新する準備を行うアプライアンスからの呼び出しを処理するために十分な容量があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50236-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="50236-p104">お使いのアプライアンスで自動更新が有効になっている場合に、マイクロソフトが重要な修正プログラムをリリースするときなどで、メンテナンス モードは役に立ちます。メンテナンス モードは、自動更新をオフにすることを決めた上で、一貫して手動での更新を実行するという場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="50236-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="50236-119">更新プログラムをインストールすると、アプライアンス戻すことのできる運用モードに終了 CcUpdate コマンドレットを実行しています。</span><span class="sxs-lookup"><span data-stu-id="50236-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50236-120">クラウド コネクタ アプライアンスを手動で更新する場合は、次のバージョンをリリースした後、60 日以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50236-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="50236-121">マイクロソフトは、新しいバージョンがリリースされた後、60 日間、過去にリリースされたバージョンのクラウドのコネクタをサポートしています</span><span class="sxs-lookup"><span data-stu-id="50236-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="50236-122">入力の種類</span><span class="sxs-lookup"><span data-stu-id="50236-122">Input Types</span></span>
<span data-ttu-id="50236-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50236-123"></span></span>

<span data-ttu-id="50236-p106">なし。Enter-CCUpdate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="50236-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="50236-126">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="50236-126">Return Types</span></span>
<span data-ttu-id="50236-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50236-127"></span></span>

<span data-ttu-id="50236-128">なし</span><span class="sxs-lookup"><span data-stu-id="50236-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="50236-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="50236-129">See also</span></span>
<span data-ttu-id="50236-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50236-130"></span></span>

[<span data-ttu-id="50236-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="50236-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

