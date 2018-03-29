---
title: 入力 CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter CcUpdate コマンドレットでは、メンテナンス モードで配置することによって更新プロセスにホスト サーバーでビジネス クラウド コネクタ版 Skype を準備します。 アプライアンスの isdrained-は、既存のすべての呼び出しは完了しますが、新しい呼び出しは拒否されます。
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a><span data-ttu-id="7f781-104">入力 CcUpdate</span><span class="sxs-lookup"><span data-stu-id="7f781-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="7f781-105">Enter CcUpdate コマンドレットでは、メンテナンス モードで配置することによって更新プロセスにホスト サーバーでビジネス クラウド コネクタ版 Skype を準備します。</span><span class="sxs-lookup"><span data-stu-id="7f781-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="7f781-106">アプライアンスは、「放電」つまり、既存すべて呼び出しは完了しますが、新しい呼び出しは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="7f781-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="7f781-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7f781-107">Parameters</span></span>

<span data-ttu-id="7f781-108">なし</span><span class="sxs-lookup"><span data-stu-id="7f781-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="7f781-109">例</span><span class="sxs-lookup"><span data-stu-id="7f781-109">Examples</span></span>
<span data-ttu-id="7f781-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7f781-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="7f781-111">例 1</span><span class="sxs-lookup"><span data-stu-id="7f781-111">Example 1</span></span>

<span data-ttu-id="7f781-112">次の例では、アプライアンスをメンテナンス モードに入れて更新プロセスに備えています。</span><span class="sxs-lookup"><span data-stu-id="7f781-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="7f781-113">解説</span><span class="sxs-lookup"><span data-stu-id="7f781-113">Detailed Description</span></span>
<span data-ttu-id="7f781-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7f781-114"></span></span>

<span data-ttu-id="7f781-115">入力 CcUpdate コマンドレットは、クラウド コネクタ アプライアンスを実行中のすべての呼び出しが完了すると、アプライアンスは、他の生産のアプライアンスに転送されるすべての新しい呼び出しが拒否されますがようにします。</span><span class="sxs-lookup"><span data-stu-id="7f781-115">The Enter-CcUpdate cmdlet will ensure that all running calls on a Cloud Connector appliance will complete, but the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="7f781-116">このコマンドレットを使用すると、エンド ・ ユーザーの呼び出しに影響を与えずに、アプライアンスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="7f781-116">This cmdlet enables you to update an appliance without affecting end users calls.</span></span> <span data-ttu-id="7f781-117">生産の残りのアプライアンスに更新する準備を行うアプライアンスからの呼び出しを処理するために十分な容量があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f781-117">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="7f781-p104">お使いのアプライアンスで自動更新が有効になっている場合に、マイクロソフトが重要な修正プログラムをリリースするときなどで、メンテナンス モードは役に立ちます。メンテナンス モードは、自動更新をオフにすることを決めた上で、一貫して手動での更新を実行するという場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7f781-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="7f781-120">更新プログラムのインストール後、Exit-CcUpdate コマンドレットを実行することによってアプライアンスを実稼働モードに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="7f781-120">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f781-121">クラウド コネクタ アプライアンスを手動で更新する場合は、次のバージョンをリリースした後、60 日以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f781-121">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="7f781-122">マイクロソフトは、新しいバージョンがリリースされた後、60 日間、過去にリリースされたバージョンのクラウドのコネクタをサポートしています</span><span class="sxs-lookup"><span data-stu-id="7f781-122">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="7f781-123">入力の種類</span><span class="sxs-lookup"><span data-stu-id="7f781-123">Input Types</span></span>
<span data-ttu-id="7f781-124"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7f781-124"></span></span>

<span data-ttu-id="7f781-p106">なし。Enter-CCUpdate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="7f781-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7f781-127">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="7f781-127">Return Types</span></span>
<span data-ttu-id="7f781-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7f781-128"></span></span>

<span data-ttu-id="7f781-129">なし</span><span class="sxs-lookup"><span data-stu-id="7f781-129">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7f781-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f781-130">See also</span></span>
<span data-ttu-id="7f781-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7f781-131"></span></span>

[<span data-ttu-id="7f781-132">終了 CcUpdate</span><span class="sxs-lookup"><span data-stu-id="7f781-132">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

