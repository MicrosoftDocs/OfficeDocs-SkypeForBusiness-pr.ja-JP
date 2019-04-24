---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Reset-CcCACertificate コマンドレットは、証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。
ms.openlocfilehash: 1ed9aaa8b7caf1edd5324d082094fa247c858853
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250876"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="88f6f-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="88f6f-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="88f6f-104">Reset-CcCACertificate コマンドレットは、証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="88f6f-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="88f6f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88f6f-105">Parameters</span></span>

<span data-ttu-id="88f6f-106">なし</span><span class="sxs-lookup"><span data-stu-id="88f6f-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="88f6f-107">例</span><span class="sxs-lookup"><span data-stu-id="88f6f-107">Examples</span></span>
<span data-ttu-id="88f6f-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="88f6f-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="88f6f-109">例 1</span><span class="sxs-lookup"><span data-stu-id="88f6f-109">Example 1</span></span>

<span data-ttu-id="88f6f-110">次の例では、証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="88f6f-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="88f6f-111">解説</span><span class="sxs-lookup"><span data-stu-id="88f6f-111">Detailed Description</span></span>
<span data-ttu-id="88f6f-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="88f6f-112"></span></span>

<span data-ttu-id="88f6f-113">ルート CA 証明書が侵害された場合やすでに安全でない場合は、ルート CA 証明書、およびルート CA によって発行されたすべての証明書を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88f6f-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="88f6f-114">Reset-CcCACertificate コマンドレットは、すべての証明書を取り消し、証明機関のアンインストールと再インストールを行い、以前の証明機関サービスに関連するすべての証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="88f6f-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="88f6f-115">詳細については、コネクタのクラウド展開のトラブルシューティングで [証明機関証明書や CMS、仲介サーバー、およびエッジ サーバーに対して発行された証明書を内部、有効期限の近くにあるかが侵害された証明書] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88f6f-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="88f6f-116">入力の種類</span><span class="sxs-lookup"><span data-stu-id="88f6f-116">Input Types</span></span>
<span data-ttu-id="88f6f-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88f6f-117"></span></span>

<span data-ttu-id="88f6f-p102">なし。Reset-CcCACertificate コマンドレットはパイプライン入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="88f6f-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="88f6f-120">戻り値の種類</span><span class="sxs-lookup"><span data-stu-id="88f6f-120">Return Types</span></span>
<span data-ttu-id="88f6f-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88f6f-121"></span></span>

<span data-ttu-id="88f6f-122">なし。</span><span class="sxs-lookup"><span data-stu-id="88f6f-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88f6f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="88f6f-123">See also</span></span>
<span data-ttu-id="88f6f-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88f6f-124"></span></span>

<span data-ttu-id="88f6f-125">[Renew-CcCACertificate](renew-cccacertificate.md) バージョン 1.4.2 のみ</span><span class="sxs-lookup"><span data-stu-id="88f6f-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="88f6f-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) バージョン 1.4.2 のみ</span><span class="sxs-lookup"><span data-stu-id="88f6f-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="88f6f-127">[Update-CcCACertificate](update-cccacertificate.md) バージョン 2.0 以降</span><span class="sxs-lookup"><span data-stu-id="88f6f-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="88f6f-128">[更新 CcServerCertificate](renew-ccservercertificate.md)バージョン 2.0 以降では</span><span class="sxs-lookup"><span data-stu-id="88f6f-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="88f6f-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="88f6f-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

