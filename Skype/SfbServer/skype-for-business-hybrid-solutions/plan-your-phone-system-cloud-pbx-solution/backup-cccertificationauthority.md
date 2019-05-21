---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。
ms.openlocfilehash: 463aab2516deec5b47e549aec67bcba6a0a80bc0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294419"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="5b4e3-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="5b4e3-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="5b4e3-104">Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="5b4e3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b4e3-105">Parameters</span></span>

<span data-ttu-id="5b4e3-106">なし</span><span class="sxs-lookup"><span data-stu-id="5b4e3-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5b4e3-107">例</span><span class="sxs-lookup"><span data-stu-id="5b4e3-107">Examples</span></span>
<span data-ttu-id="5b4e3-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b4e3-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="5b4e3-109">例 1</span><span class="sxs-lookup"><span data-stu-id="5b4e3-109">Example 1</span></span>

<span data-ttu-id="5b4e3-110">次の例では、証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="5b4e3-111">解説</span><span class="sxs-lookup"><span data-stu-id="5b4e3-111">Detailed Description</span></span>
<span data-ttu-id="5b4e3-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5b4e3-112"></span></span>

<span data-ttu-id="5b4e3-113">証明機関のバックアップは、障害が発生した場合に備えて、同じ証明書を使ってクラウドコネクタのアプライアンスを再展開する場合や、新しいハードウェアにアプライアンスを移行する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="5b4e3-114">このコマンドは、クラウドコネクタ証明機関サービスのコピーを AD サーバーから "\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12" に保存します。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5b4e3-115">入力の種類</span><span class="sxs-lookup"><span data-stu-id="5b4e3-115">Input Types</span></span>
<span data-ttu-id="5b4e3-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b4e3-116"></span></span>

<span data-ttu-id="5b4e3-p102">なし。Backup-CcCertificationAuthority コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5b4e3-119">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="5b4e3-119">Return Types</span></span>
<span data-ttu-id="5b4e3-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b4e3-120"></span></span>

<span data-ttu-id="5b4e3-121">なし</span><span class="sxs-lookup"><span data-stu-id="5b4e3-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b4e3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b4e3-122">See also</span></span>
<span data-ttu-id="5b4e3-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b4e3-123"></span></span>

[<span data-ttu-id="5b4e3-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="5b4e3-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

