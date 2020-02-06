---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile コマンドレットを使用すると、Skype for Business Cloud Connector エディションのサイト共有ディレクトリの CA フォルダーにある証明機関サービスのバックアップファイルが削除されます。
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824293"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="5b442-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="5b442-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="5b442-104">CcCertificationAuthorityFile コマンドレットを使用すると、Skype for Business Cloud Connector&lt;エディション&gt;のサイト共有ディレクトリの下にある CA フォルダーで、証明機関サービスのバックアップファイル "SiteRootDirectory \CA\SfB CCE Root. p12" が削除されます。</span><span class="sxs-lookup"><span data-stu-id="5b442-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="5b442-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b442-105">Parameters</span></span>

<span data-ttu-id="5b442-106">なし</span><span class="sxs-lookup"><span data-stu-id="5b442-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5b442-107">例</span><span class="sxs-lookup"><span data-stu-id="5b442-107">Examples</span></span>
<span data-ttu-id="5b442-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b442-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5b442-109">例 1</span><span class="sxs-lookup"><span data-stu-id="5b442-109">Example 1</span></span>

<span data-ttu-id="5b442-110">次の例では、サイトの共有ディレクトリの&lt;下&gt;にある CA フォルダーの証明機関サービスバックアップファイル "SiteRootDirectory \CA\SfB CCE ルート. p12" を削除します。</span><span class="sxs-lookup"><span data-stu-id="5b442-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="5b442-111">入力の種類</span><span class="sxs-lookup"><span data-stu-id="5b442-111">Input Types</span></span>
<span data-ttu-id="5b442-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b442-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5b442-p101">なし。Remove-CcCertificationAuthorityFile コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="5b442-p101">None. The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5b442-115">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="5b442-115">Return Types</span></span>
<span data-ttu-id="5b442-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b442-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5b442-117">なし</span><span class="sxs-lookup"><span data-stu-id="5b442-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b442-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b442-118">See also</span></span>
<span data-ttu-id="5b442-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b442-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="5b442-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="5b442-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

