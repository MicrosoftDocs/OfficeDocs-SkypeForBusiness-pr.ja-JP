---
title: 'Lync Server 2013: 証明書レポートの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a584f331deaf702305367042c6c40679ffb7099f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="242e5-102">Lync Server 2013 の証明書レポートの確認</span><span class="sxs-lookup"><span data-stu-id="242e5-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="242e5-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="242e5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="242e5-104">証明書レポートには、推奨される Lync Server 2013 の展開に必要なすべての証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="242e5-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="242e5-105">入力されたサブジェクト名とサブジェクトの別名の計画ツールアカウント。</span><span class="sxs-lookup"><span data-stu-id="242e5-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="242e5-106">未編集のままになっている既定のテキストは、証明書の要求と発行を担当するチームの潜在的な課題を表している場合があります。</span><span class="sxs-lookup"><span data-stu-id="242e5-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="242e5-107">証明書情報には、証明書が主としてどこから発行されるかについての情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="242e5-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="242e5-108">インフラストラクチャが内部公開キー基盤 (PKI) を持たない場合、すべての証明書はパブリック証明書プロバイダーを介して要求することができます。</span><span class="sxs-lookup"><span data-stu-id="242e5-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="242e5-109">拡張キー使用法 (EKU) およびレポートの [割り当て] フィールドは、それぞれの証明書の目的および場所を知るのに非常に有用です。</span><span class="sxs-lookup"><span data-stu-id="242e5-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="242e5-110">![証明書管理レポート](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "証明書管理レポート")</span><span class="sxs-lookup"><span data-stu-id="242e5-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="242e5-111">展開内の各証明書の用途と目的を慎重に確認し、理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="242e5-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="242e5-112">証明書の内容についての質問がある場合は、どのサーバーまたはサービスがどのようなものになっているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="242e5-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="242e5-113">Lync Server 2013 の証明書は、主に次の2つの目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="242e5-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="242e5-114">相互トランスポート層セキュリティ (MTLS) –通信に関与するコンピューターはそれぞれ、id を証明する証明書を別のコンピューターに提示します。</span><span class="sxs-lookup"><span data-stu-id="242e5-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="242e5-115">これは、サーバー認証と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="242e5-115">This is known as server authentication.</span></span> <span data-ttu-id="242e5-116">通信は、各コンピューターが他のコンピューターの id を信頼するまで開始できません。</span><span class="sxs-lookup"><span data-stu-id="242e5-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="242e5-117">暗号化 –  暗号化 (Secure Sockets Layer (SSL) およびトランスポート層セキュリティ (TLS)) は、セキュリティで保護された通信およびプライバシーの保護を支援し、信頼性の高い通信およびコラボレーション システムを作成するための重要な手段です。</span><span class="sxs-lookup"><span data-stu-id="242e5-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="242e5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="242e5-118">See Also</span></span>


[<span data-ttu-id="242e5-119">Lync Server 2013 での管理者レポートの確認</span><span class="sxs-lookup"><span data-stu-id="242e5-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

