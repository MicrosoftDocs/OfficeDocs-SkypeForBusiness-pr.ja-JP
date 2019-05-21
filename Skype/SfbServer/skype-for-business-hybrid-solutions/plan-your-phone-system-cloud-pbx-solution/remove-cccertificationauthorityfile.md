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
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile コマンドレットを使用すると、Skype for Business Cloud Connector エディションのサイト共有ディレクトリの CA フォルダーにある証明機関サービスのバックアップファイルが削除されます。
ms.openlocfilehash: 3251c3f608b52d217e7db04d7b5081ff73c0b487
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287091"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="45294-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="45294-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="45294-104">CcCertificationAuthorityFile コマンドレットを使用すると、Skype for Business Cloud Connector&lt;の&gt;サイト共有ディレクトリの下にある CA フォルダー内の証明機関サービスバックアップファイル "SiteRootDirectory \CA\SfB CCE Root. p12" が削除されます。Edition.</span><span class="sxs-lookup"><span data-stu-id="45294-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="45294-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45294-105">Parameters</span></span>

<span data-ttu-id="45294-106">なし</span><span class="sxs-lookup"><span data-stu-id="45294-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="45294-107">例</span><span class="sxs-lookup"><span data-stu-id="45294-107">Examples</span></span>
<span data-ttu-id="45294-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="45294-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="45294-109">例 1</span><span class="sxs-lookup"><span data-stu-id="45294-109">Example 1</span></span>

<span data-ttu-id="45294-110">次の例では、サイトの共有ディレクトリの&lt;下&gt;にある CA フォルダーの証明機関サービスバックアップファイル "SiteRootDirectory \CA\SfB CCE ルート. p12" を削除します。</span><span class="sxs-lookup"><span data-stu-id="45294-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="45294-111">入力の種類</span><span class="sxs-lookup"><span data-stu-id="45294-111">Input Types</span></span>
<span data-ttu-id="45294-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45294-112"></span></span>

<span data-ttu-id="45294-p101">なし。Remove-CcCertificationAuthorityFile コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="45294-p101">None. The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="45294-115">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="45294-115">Return Types</span></span>
<span data-ttu-id="45294-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45294-116"></span></span>

<span data-ttu-id="45294-117">なし</span><span class="sxs-lookup"><span data-stu-id="45294-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45294-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="45294-118">See also</span></span>
<span data-ttu-id="45294-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45294-119"></span></span>

[<span data-ttu-id="45294-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="45294-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

