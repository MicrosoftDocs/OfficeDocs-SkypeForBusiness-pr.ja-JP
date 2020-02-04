---
title: 'Lync Server 2013: ドキュメント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaeb06f1d9144d0c6f28984d509b3777673e10f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="1b311-102">Lync Server 2013 のドキュメント</span><span class="sxs-lookup"><span data-stu-id="1b311-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b311-103">_**最終更新日:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="1b311-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="1b311-104">MOF モデルは、多くのサービス管理機能で構成されています。</span><span class="sxs-lookup"><span data-stu-id="1b311-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="1b311-105">タスクの実行方法とタイミングについてのドキュメントは、同じチームまたは他のチームのメンバーと共有できます。</span><span class="sxs-lookup"><span data-stu-id="1b311-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="1b311-106">ドキュメントの保存と共有の方法は、関数の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1b311-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="1b311-107">たとえば、システム管理の手順は Word 文書として保存されている可能性があります。これは、頻繁に印刷および参照される可能性が高いためです。</span><span class="sxs-lookup"><span data-stu-id="1b311-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="1b311-108">検索とインデックス作成を簡単にするために、構成管理情報が自動的に生成され、データベースに保存されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1b311-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="1b311-109">ドキュメントによっては、制限されていることがあります。</span><span class="sxs-lookup"><span data-stu-id="1b311-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="1b311-110">ドキュメント管理システム</span><span class="sxs-lookup"><span data-stu-id="1b311-110">Document management systems</span></span>

<span data-ttu-id="1b311-111">ドキュメント管理システムはドキュメントの中央リポジトリとして機能し、ドキュメントの最新のリビジョンのみが利用できるようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1b311-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="1b311-112">以前のバージョンのドキュメントを参照用にアーカイブすることを検討することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b311-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="1b311-113">Lync Server は、このタスクに適した機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b311-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="1b311-114">データベース</span><span class="sxs-lookup"><span data-stu-id="1b311-114">Databases</span></span>

<span data-ttu-id="1b311-115">データベースの使用に適したいくつかのツールと管理機能について説明しました。</span><span class="sxs-lookup"><span data-stu-id="1b311-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="1b311-116">構成管理プロセスでは、インデックス作成と検索が必要な大量のデータを格納する自動化されたプロセスを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b311-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="1b311-117">サポートスタッフは、新しい問題のトラブルシューティングを行うときに、過去の問題と解決策のデータベースを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="1b311-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="1b311-118">目的に応じて異なるデータベースが使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b311-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="1b311-119">これらのデータベースをリンクするか、結合するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1b311-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="1b311-120">たとえば、サービスデスクが一般的なテーマに関するいくつかの問題を特定している場合 (特定のネットワークアダプターに関する問題の原因となる新しいソフトウェアなど)、サポート担当者は構成データベースを照会して、影響を受ける可能性のあるコンピューターの数を予測することができます。</span><span class="sxs-lookup"><span data-stu-id="1b311-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

