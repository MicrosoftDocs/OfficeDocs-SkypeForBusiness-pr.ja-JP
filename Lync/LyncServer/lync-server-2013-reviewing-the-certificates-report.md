---
title: 'Lync Server 2013: 証明書レポートの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="5b2da-102">Lync Server 2013 で証明書レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="5b2da-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b2da-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5b2da-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5b2da-104">証明書レポートには、Lync 2013 Server の推奨される展開で必要なすべての証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b2da-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="5b2da-105">入力されたサブジェクト名とサブジェクトの代替名の計画ツールアカウント。</span><span class="sxs-lookup"><span data-stu-id="5b2da-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="5b2da-106">未編集として残っている既定のテキストは、証明書の要求と発行を担当するチームの潜在的な問題を表している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5b2da-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="5b2da-107">証明書情報には、証明書の一般的な発行元に関する情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b2da-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="5b2da-108">インフラストラクチャに内部の公開キー基盤 (PKI) が配置されていない場合は、すべての証明書を公開証明書プロバイダーを通じて要求できます。</span><span class="sxs-lookup"><span data-stu-id="5b2da-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="5b2da-109">レポートの拡張キー使用法 (EKU) とフィールドへの割り当ては、各証明書の目的と場所を理解するのに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5b2da-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="5b2da-110">![証明書管理者レポート](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "証明書管理者レポート")</span><span class="sxs-lookup"><span data-stu-id="5b2da-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="5b2da-111">展開内のそれぞれの証明書の使用法および目的を注意深く確認し、しっかりと理解してください。</span><span class="sxs-lookup"><span data-stu-id="5b2da-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="5b2da-112">証明書の役割についての質問がある場合は、どのサーバーまたはサービスが何を対象としているのかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b2da-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="5b2da-113">Lync Server 2013 の証明書は、主に次の2つの目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="5b2da-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="5b2da-p103">相互トランスポート層セキュリティ (MTLS) - 通信にかかわっているコンピューターがそれぞれ証明書を提示し、他のコンピューターに対して自分の ID を証明します。これは、サーバー認証として知られています。通信は、それぞれのコンピューターが他のコンピューターの ID を信頼するまで開始されません。</span><span class="sxs-lookup"><span data-stu-id="5b2da-p103">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer. This is known as server authentication. Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="5b2da-117">暗号化 ‐ 暗号化 (Secure Sockets Layer (SSL) およびトランスポート層セキュリティ (TLS)) は、セキュリティで保護された通信およびプライバシーの保護を支援し、信頼性の高い通信およびコラボレーション システムを作成するための重要な手段です。</span><span class="sxs-lookup"><span data-stu-id="5b2da-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5b2da-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b2da-118">See Also</span></span>


[<span data-ttu-id="5b2da-119">Lync Server 2013 での管理者レポートの確認</span><span class="sxs-lookup"><span data-stu-id="5b2da-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

