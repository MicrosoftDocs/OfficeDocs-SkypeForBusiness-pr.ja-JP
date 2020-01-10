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
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003027"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="6f7d7-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="6f7d7-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="6f7d7-104">Backup-CcCertificationAuthority コマンドレットは、Skype for Business Cloud Connector エディションの証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="6f7d7-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="6f7d7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f7d7-105">Parameters</span></span>

<span data-ttu-id="6f7d7-106">なし</span><span class="sxs-lookup"><span data-stu-id="6f7d7-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6f7d7-107">例</span><span class="sxs-lookup"><span data-stu-id="6f7d7-107">Examples</span></span>
<span data-ttu-id="6f7d7-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6f7d7-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="6f7d7-109">例 1</span><span class="sxs-lookup"><span data-stu-id="6f7d7-109">Example 1</span></span>

<span data-ttu-id="6f7d7-110">次の例では、証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="6f7d7-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="6f7d7-111">解説</span><span class="sxs-lookup"><span data-stu-id="6f7d7-111">Detailed Description</span></span>
<span data-ttu-id="6f7d7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6f7d7-112"></span></span>

<span data-ttu-id="6f7d7-113">証明機関のバックアップは、障害が発生した場合に備えて、同じ証明書を使ってクラウドコネクタのアプライアンスを再展開する場合や、新しいハードウェアにアプライアンスを移行する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6f7d7-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="6f7d7-114">このコマンドは、クラウドコネクタ証明機関サービスのコピーを AD サーバーから "\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12" に保存します。</span><span class="sxs-lookup"><span data-stu-id="6f7d7-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="6f7d7-115">入力の種類</span><span class="sxs-lookup"><span data-stu-id="6f7d7-115">Input Types</span></span>
<span data-ttu-id="6f7d7-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f7d7-116"></span></span>

<span data-ttu-id="6f7d7-p102">なし。Backup-CcCertificationAuthority コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6f7d7-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6f7d7-119">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="6f7d7-119">Return Types</span></span>
<span data-ttu-id="6f7d7-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f7d7-120"></span></span>

<span data-ttu-id="6f7d7-121">なし</span><span class="sxs-lookup"><span data-stu-id="6f7d7-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6f7d7-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f7d7-122">See also</span></span>
<span data-ttu-id="6f7d7-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f7d7-123"></span></span>

[<span data-ttu-id="6f7d7-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="6f7d7-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

