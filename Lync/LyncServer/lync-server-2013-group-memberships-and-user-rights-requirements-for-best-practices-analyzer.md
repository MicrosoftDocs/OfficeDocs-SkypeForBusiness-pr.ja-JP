---
title: ベストプラクティスアナライザーのグループメンバーシップとユーザー権限の要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9561736fc6dce1649d0a3dd29e15a7d88500a38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="4d050-102">Lync Server 2013 でのベストプラクティスアナライザーのグループメンバーシップとユーザー権限の要件</span><span class="sxs-lookup"><span data-stu-id="4d050-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d050-103">_**最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="4d050-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="4d050-104">ベストプラクティスアナライザーを正常に実行するには、ログオンに使用するユーザーアカウントが、ローカルコンピューターの管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d050-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="4d050-105">さらに、環境をスキャンするには、ユーザーアカウントが次のグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d050-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="4d050-106">**ドメイン管理者**   が、Active Directory ドメインサービスの情報を列挙し、ドメインコントローラーとグローバルカタログサーバー上の Windows Management Instrumentation (WMI) プロバイダーに電話をかけます。</span><span class="sxs-lookup"><span data-stu-id="4d050-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="4d050-107">**管理者**   は、各 Lync server 2013 内部コンピューターと各エッジサーバーで Windows Management Instrumentation (WMI) プロバイダーを呼び出し、レジストリにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d050-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="4d050-108">**RTCUniversalReadOnlyAdmins**   フルまたは委任された読み取り専用の Lync Server 2013 管理者権限。</span><span class="sxs-lookup"><span data-stu-id="4d050-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="4d050-109">**Exchange の管理者**   は、Microsoft exchange 組織でのみ exchange の管理者のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d050-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="4d050-110">ユーザーアカウントに十分なユーザー権限がない場合は、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4d050-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="4d050-111">コマンドプロンプトで、 **runas**コマンドを使用して、十分なユーザー権限があるアカウントでツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d050-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="4d050-112">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4d050-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="4d050-113">[ **Active Directory に接続する**] ページで、ベストプラクティスアナライザーを実行するために使用する予定のアカウントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="4d050-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="4d050-114">[**詳細ログインオプションの表示] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="4d050-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="4d050-115">Active Directory ドメインサービスへの接続用に1つ、Lync Server 2013 エッジサーバーへの接続用、および Exchange サーバーへの接続用の3つのアカウントを入力できます。</span><span class="sxs-lookup"><span data-stu-id="4d050-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="4d050-116">これらのいずれかのアカウントを指定しない場合、ログオンに使用したユーザーアカウントとベストプラクティスアナライザーを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d050-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

