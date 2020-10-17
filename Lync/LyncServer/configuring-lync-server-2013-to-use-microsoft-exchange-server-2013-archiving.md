---
title: Microsoft Exchange Server 2013 アーカイブを使用するように Lync Server 2013 を構成する
description: Microsoft Exchange Server 2013 アーカイブを使用するように Lync Server 2013 を構成する。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b0673071ec38246e366fe7556b39bd495895d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542943"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="f90ce-103">Microsoft Exchange Server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="f90ce-103">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f90ce-104">_**トピックの最終更新日:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="f90ce-104">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="f90ce-105">Microsoft Lync Server 2013 を使用すると、管理者は、インスタントメッセージングと Web 会議のトランスクリプトを SQL Server データベースではなく、ユーザーの Microsoft Exchange Server 2013 メールボックスにアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-105">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="f90ce-106">管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="f90ce-107">Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="f90ce-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="f90ce-108">このフォルダーはエンドユーザーには表示されませんが、フォルダーは Exchange 検索エンジンによってインデックスが作成され、Exchange メールボックスの検索や Microsoft SharePoint Server 2013 を使用して検出できます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-108">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="f90ce-109">情報は、Exchange In-Place の保持機能 (メールやその他の Exchange 通信のアーカイブを担当する) で使用されるものと同じフォルダーに格納されているため、管理者は1つのツールを使用して、ユーザーに対してアーカイブされたすべての電子通信を検索できます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f90ce-110">Lync 会話のアーカイブを完全に無効にするには、Lync 会話履歴も無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-110">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="f90ce-111">詳細については、以下のトピックを参照してください。 Lync Server 2013、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>、および<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-csclientpolicy</A><A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">で、内部通信と外部通信のアーカイブを管理</A>する。</span><span class="sxs-lookup"><span data-stu-id="f90ce-111">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="f90ce-112">Exchange 2013 にトランスクリプトをアーカイブするには、2つのサーバー間でサーバー間認証を構成することから始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-112">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="f90ce-113">サーバー間認証が行われた後、Microsoft Lync Server 2013 で次のタスクを実行できます (セットアップと構成によっては、これらのタスクをすべて完了する必要がない場合があることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="f90ce-113">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="f90ce-114">Lync Server アーカイブ構成設定を変更して、Exchange アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-114">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="f90ce-115">この手順はすべての展開で必要です。</span><span class="sxs-lookup"><span data-stu-id="f90ce-115">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="f90ce-116">ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-116">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="f90ce-117">この手順はすべての展開で必要です。</span><span class="sxs-lookup"><span data-stu-id="f90ce-117">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="f90ce-118">各ユーザーの ExchangeArchivingPolicy プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="f90ce-119">この手順は、Lync Server でのみ必要であり、Exchange が異なるフォレストに配置されています。</span><span class="sxs-lookup"><span data-stu-id="f90ce-119">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="f90ce-120">手順 1: Exchange アーカイブを有効にする</span><span class="sxs-lookup"><span data-stu-id="f90ce-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="f90ce-121">Lync Server でのアーカイブは、主にアーカイブ構成設定を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-121">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="f90ce-122">Lync Server 2013 をインストールすると、これらの設定の単一のグローバルコレクションが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-122">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="f90ce-123">(必要に応じて、管理者はサイトスコープでアーカイブ設定の新しいコレクションを作成できます)。既定では、グローバル設定でアーカイブが有効になっていません。また、これらの設定では Exchange アーカイブが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f90ce-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="f90ce-124">Exchange アーカイブ管理者を使用するには、これらの構成設定で EnableArchiving と Enableexchangeアーカイビングプロパティの両方を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-124">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="f90ce-125">EnableArchiving プロパティには、次の3つの値のいずれかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-125">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="f90ce-126">**なし**。</span><span class="sxs-lookup"><span data-stu-id="f90ce-126">**None**.</span></span> <span data-ttu-id="f90ce-127">アーカイブが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f90ce-127">Archiving is disabled.</span></span> <span data-ttu-id="f90ce-128">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="f90ce-128">This is the default value.</span></span> <span data-ttu-id="f90ce-129">EnableArchiving が [なし] に設定されている場合は、Lync Server アーカイブデータベースまたは Exchange 2013 のいずれかにアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="f90ce-129">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="f90ce-130">**Imonly**。</span><span class="sxs-lookup"><span data-stu-id="f90ce-130">**ImOnly**.</span></span> <span data-ttu-id="f90ce-131">インスタントメッセージのトランスクリプトのみがアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="f90ce-132">Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-132">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="f90ce-133">Exchange のアーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-133">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="f90ce-134">**Imandwebconf**。</span><span class="sxs-lookup"><span data-stu-id="f90ce-134">**ImAndWebConf**.</span></span> <span data-ttu-id="f90ce-135">インスタントメッセージのトランスクリプトと Web 会議のトランスクリプトは、両方ともアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="f90ce-136">Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-136">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="f90ce-137">Exchange のアーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-137">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="f90ce-138">EnableExchangeArchiving プロパティは、ブール値です。 EnableExchangeArchiving を True ($True) に設定して、Exchange アーカイブを有効にするか、EnableExchangeArchiving を False ($False) に設定して Exchange アーカイブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="f90ce-139">たとえば、次のコマンドを実行すると、インスタントメッセージングトランスクリプトのアーカイブが有効になり、Exchange アーカイブも有効になります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="f90ce-140">Exchange アーカイブを無効にするには、次のようなコマンドを使用します。これにより、インスタントメッセージングアーカイブは有効になりますが、Exchange へのアーカイブが無効になります (つまり、トランスクリプトは Lync Server にアーカイブされます)。</span><span class="sxs-lookup"><span data-stu-id="f90ce-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="f90ce-141">EnableArchiving プロパティが None に設定されている場合、Lync Server はインスタントメッセージングと Web 会議のトランスクリプトをまったくアーカイブしません。</span><span class="sxs-lookup"><span data-stu-id="f90ce-141">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="f90ce-142">この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="f90ce-143">Exchange アーカイブは、Lync Server コントロールパネルを使用して有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-143">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="f90ce-144">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-144">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="f90ce-145">コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="f90ce-146">[**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="f90ce-147">[**編集 アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="f90ce-148">アーカイブするアイテムを選択した後、[ **Exchange Server 統合** ] チェックボックスをオンにして、exchange アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="f90ce-149">Exchange アーカイブを無効にするには、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-149">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f90ce-150">[<STRONG>アーカイブ設定</STRONG>] が [<STRONG>アーカイブを無効にする</STRONG>] に設定されていると [<STRONG>Exchange Server の統合</STRONG>] チェック ボックスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="f90ce-150">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="f90ce-151">最初にアーカイブを有効にしてから、Exchange アーカイブを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-151">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="f90ce-152">Lync Server 2013 と Exchange 2013 が同じフォレストに存在する場合、個々のユーザー (または少なくとも Exchange 2013 の電子メールアカウントを持つユーザー) のアーカイブは、Exchange In-Place 保持ポリシーを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-152">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="f90ce-153">以前のバージョンの Exchange に所属しているユーザーがいる場合は、それらのユーザーのアーカイブが Lync Server アーカイブポリシーを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="f90ce-154">Exchange 2013 上のアカウントを持つユーザーのみが、Lync トランスクリプトを Exchange にアーカイブできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f90ce-154">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="f90ce-155">Lync Server 2013 と Exchange 2013 が異なるフォレストに配置されている場合は、個々のユーザーアカウントの ExchangeArchivingPolicy プロパティを構成することによって、個々のユーザーのアーカイブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-155">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="f90ce-156">詳細については、手順3を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f90ce-156">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="f90ce-157">手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする</span><span class="sxs-lookup"><span data-stu-id="f90ce-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="f90ce-158">アーカイブ (および Exchange アーカイブ) を有効にした後、適切なアーカイブポリシーを変更して、ユーザーセッションが実際にアーカイブされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="f90ce-159">アーカイブを有効にする (手順 1) だけでは、Lync Server でインスタントメッセージングと Web 会議のトランスクリプトのアーカイブが開始されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f90ce-159">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="f90ce-160">このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="f90ce-161">Lync Server 2013 をインストールするときは、次の2つのプロパティを含む単一のグローバルなアーカイブポリシーもインストールします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-161">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="f90ce-p119">**ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="f90ce-p120">**ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="f90ce-166">既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="f90ce-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="f90ce-167">グローバルポリシーを変更するには、Lync Server 管理シェルと Set-CsArchivingPolicy コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-167">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="f90ce-168">次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-168">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="f90ce-p122">また、New-CsArchivingPolicy を使用して、サイト スコープまたはユーザーごとのスコープで新しいポリシーを作成することもできます。たとえば、次のコマンドを実行すると RedmondArchivingPolicy という名前の新しいユーザーごとのアーカイブ ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="f90ce-p123">ユーザーごとのポリシーを作成した場合は、そのポリシーを適切なユーザーに割り当てる必要があります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="f90ce-173">また、アーカイブポリシーは、Lync Server コントロールパネルを使用して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-173">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="f90ce-174">コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="f90ce-175">既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="f90ce-176">新しいアーカイブポリシーを作成するには、[ **新規** ] をクリックし、[ **サイトポリシー** ] または [ **ユーザーポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="f90ce-177">新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="f90ce-178">手順 3: ExchangeArchivingPolicy プロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="f90ce-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="f90ce-179">Lync Server 2013 と Exchange 2013 が異なるフォレストに配置されている場合は、アーカイブ構成設定で Exchange アーカイブを有効にできるだけではありません。これにより、インスタントメッセージングと Web 会議のトランスクリプトは Exchange にアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="f90ce-179">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="f90ce-180">代わりに、各関連する Lync Server ユーザーアカウントで ExchangeArchivingPolicy プロパティを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="f90ce-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="f90ce-181">このプロパティには、次の4つの値のいずれかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-181">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="f90ce-182">ない.</span><span class="sxs-lookup"><span data-stu-id="f90ce-182">Uninitialized.</span></span> <span data-ttu-id="f90ce-183">アーカイブが、ユーザーの Exchange メールボックスに対して構成された In-Place 保持設定に基づいて行われることを示します。ユーザーのメールボックスで In-Place ホールドが有効になっていない場合、ユーザーは自分のメッセージングと Web 会議のトランスクリプトを Lync Server にアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="f90ce-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="f90ce-184">**UseLyncArchivingPolicy**。</span><span class="sxs-lookup"><span data-stu-id="f90ce-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="f90ce-185">ユーザーのインスタントメッセージングおよび Web 会議のトランスクリプトを Exchange ではなく Lync Server にアーカイブする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="f90ce-186">**Noarchiving**。</span><span class="sxs-lookup"><span data-stu-id="f90ce-186">**NoArchiving**.</span></span> <span data-ttu-id="f90ce-187">ユーザーのインスタントメッセージングと Web 会議のトランスクリプトをまったくアーカイブしないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="f90ce-188">この設定は、ユーザーに割り当てられた Lync Server アーカイブポリシーよりも優先されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f90ce-188">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="f90ce-189">**ArchivingToExchange**。</span><span class="sxs-lookup"><span data-stu-id="f90ce-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="f90ce-190">ユーザーのメールボックスに割り当てられているかどうかにかかわら In-Place ず、ユーザーのインスタントメッセージングおよび Web 会議のトランスクリプトを Exchange にアーカイブする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="f90ce-191">たとえば、インスタントメッセージングと Web 会議のトランスクリプトを常に Exchange にアーカイブするようにユーザーアカウントを構成するには、Lync Server 管理シェルから次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="f90ce-192">ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f90ce-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="f90ce-193">ExchangeArchivingPolicy プロパティの値を構成するには、Lync Server 管理シェル (および Windows PowerShell) を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f90ce-193">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="f90ce-194">このプロパティは、Lync Server コントロールパネルの管理者には公開されません。</span><span class="sxs-lookup"><span data-stu-id="f90ce-194">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="f90ce-195">特定のアーカイブ ポリシーを割り当てられているすべてのユーザーの一覧を表示するには、次のようなコマンドを使用します。このコマンドを実行すると、ExchangeArchivingPolicy プロパティが Uninitialized に設定されているすべてのユーザーの Active Directory 表示名が取得されます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="f90ce-196">同様に、次のコマンドを実行すると、ExchangeArchivingPolicy プロパティが UseLyncArchivingPolicy に設定されていないユーザーの表示名が取得されます。</span><span class="sxs-lookup"><span data-stu-id="f90ce-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

