---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。
ms.openlocfilehash: 2f85a4da58a586852b3331f1f8e482ee17e29e02
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234552"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="d042a-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="d042a-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="d042a-104">Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="d042a-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="d042a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d042a-105">Parameters</span></span>

<span data-ttu-id="d042a-106">なし</span><span class="sxs-lookup"><span data-stu-id="d042a-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d042a-107">例</span><span class="sxs-lookup"><span data-stu-id="d042a-107">Examples</span></span>
<span data-ttu-id="d042a-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d042a-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="d042a-109">例 1</span><span class="sxs-lookup"><span data-stu-id="d042a-109">Example 1</span></span>

<span data-ttu-id="d042a-110">次の例では、証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="d042a-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="d042a-111">解説</span><span class="sxs-lookup"><span data-stu-id="d042a-111">Detailed Description</span></span>
<span data-ttu-id="d042a-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d042a-112"></span></span>

<span data-ttu-id="d042a-113">同じ証明書、障害発生時にクラウドのコネクタのアプライアンスを再展開する場合、またはアプライアンスを新しいハードウェアに移動する場合は、証明機関のバックアップは役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="d042a-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="d042a-114">コマンドに AD サーバーからクラウド コネクタ証明機関サービスのコピーを保存する"\<SiteRootDirectory\>\CA\SfB CCE Root.p12」です。</span><span class="sxs-lookup"><span data-stu-id="d042a-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="d042a-115">入力の種類</span><span class="sxs-lookup"><span data-stu-id="d042a-115">Input Types</span></span>
<span data-ttu-id="d042a-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d042a-116"></span></span>

<span data-ttu-id="d042a-p102">なし。Backup-CcCertificationAuthority コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="d042a-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d042a-119">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="d042a-119">Return Types</span></span>
<span data-ttu-id="d042a-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d042a-120"></span></span>

<span data-ttu-id="d042a-121">なし</span><span class="sxs-lookup"><span data-stu-id="d042a-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d042a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d042a-122">See also</span></span>
<span data-ttu-id="d042a-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d042a-123"></span></span>

[<span data-ttu-id="d042a-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="d042a-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

