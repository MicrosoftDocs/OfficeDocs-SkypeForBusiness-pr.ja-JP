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
ms.openlocfilehash: b552f9aadfe9ed4c99c12b7e3f9524e4de143e23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="937c8-102">Lync Server 2013 のベストプラクティスアナライザーのグループメンバーシップとユーザー権限の要件</span><span class="sxs-lookup"><span data-stu-id="937c8-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="937c8-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="937c8-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="937c8-p101">ベスト プラクティス アナライザーを正常に実行するには、ログオンで使用したユーザー アカウントがローカル コンピューターの Administrators グループのメンバーである必要があります。また、環境をスキャンするには、ユーザー アカウントが次のグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="937c8-p101">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer. Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="937c8-106">**ドメイン管理者**   は、Active Directory ドメインサービスの情報を列挙し、ドメインコントローラーおよびグローバルカタログサーバーの Windows Management Instrumentation (WMI) プロバイダーを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="937c8-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="937c8-107">**管理者**   は、各 Lync server 2013 内部コンピューターと各エッジサーバーで、Windows Management Instrumentation (WMI) プロバイダを呼び出し、レジストリにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="937c8-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="937c8-108">**RTCUniversalReadOnlyAdmins**   Full または委任されたすべての読み取り専用 Lync Server 2013 の管理者権限。</span><span class="sxs-lookup"><span data-stu-id="937c8-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="937c8-109">**Exchange view only 管理者**   完全または委任された Microsoft exchange 組織の管理者のみ。</span><span class="sxs-lookup"><span data-stu-id="937c8-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="937c8-110">ユーザー アカウントで十分なユーザー権限がない場合、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="937c8-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="937c8-111">コマンド プロンプトで、**runas** コマンドを使って十分なユーザー権限があるアカウントからツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="937c8-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="937c8-112">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="937c8-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="937c8-113">[ **Active Directory への接続**] ページで、ベストプラクティスアナライザーを実行するために使用する予定のアカウントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="937c8-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="937c8-114">[**詳細なログインオプションの表示] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="937c8-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="937c8-115">3つのアカウントを入力できます。1つは Active Directory ドメインサービスへの接続用、もう1つは Lync Server 2013 エッジサーバーへの接続用、もう1つは Exchange サーバーへの接続用です。</span><span class="sxs-lookup"><span data-stu-id="937c8-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="937c8-116">これらのアカウントのいずれも指定しない場合は、ログオンしてベストプラクティスアナライザーを実行するために使用したユーザーアカウントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="937c8-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

