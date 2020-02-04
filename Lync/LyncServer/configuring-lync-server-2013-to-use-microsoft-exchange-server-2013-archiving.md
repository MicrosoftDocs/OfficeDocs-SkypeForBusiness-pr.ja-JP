---
title: Microsoft Exchange Server 2013 アーカイブを使用するように Lync Server 2013 を構成する
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
ms.openlocfilehash: 3b163b0ce3324455f8a80eca7be5c1423b302a3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="bd52b-102">Microsoft Exchange Server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="bd52b-102">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd52b-103">_**最終更新日:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="bd52b-103">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="bd52b-104">Microsoft Lync Server 2013 を使用すると、管理者は、インスタントメッセージと Web 会議のトランスクリプトを SQL Server データベースではなく、ユーザーの Microsoft Exchange Server 2013 メールボックスにアーカイブするオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-104">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="bd52b-105">管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-105">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="bd52b-106">Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="bd52b-106">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="bd52b-107">このフォルダーは、エンドユーザーには表示されませんが、Exchange のメールボックス検索や Microsoft SharePoint Server 2013 を使用すると、フォルダーは Exchange 検索エンジンによってインデックス処理され、検出できます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-107">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="bd52b-108">情報は、Exchange のインプレースホールド機能で使用されているものと同じフォルダー (メールのアーカイブおよびその他の Exchange 通信を担当します) に保存されているため、管理者は、1つのツールを使用してアーカイブされているすべての電子通信を検索することができます。ユーザーズ.</span><span class="sxs-lookup"><span data-stu-id="bd52b-108">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd52b-109">Lync の会話のアーカイブを完全に無効にするには、Lync の会話履歴も無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-109">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="bd52b-110">詳細については、次のトピックを参照してください。 <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Lync Server 2013 での内部および外部通信のアーカイブの管理</A>、<A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">新しい-csclientpolicy</A>、および<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set csclientpolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="bd52b-110">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="bd52b-111">Exchange 2013 にトランスクリプトをアーカイブするには、最初に2つのサーバー間でサーバー間認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-111">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="bd52b-112">サーバー間認証が行われたら、Microsoft Lync Server 2013 で次のタスクを実行できます (ただし、セットアップと構成によっては、これらのすべてのタスクを完了する必要がない場合があることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="bd52b-112">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="bd52b-113">Lync Server のアーカイブ構成設定を変更して、Exchange のアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-113">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="bd52b-114">この手順はすべての展開で必要です。</span><span class="sxs-lookup"><span data-stu-id="bd52b-114">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="bd52b-115">ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-115">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="bd52b-116">この手順はすべての展開で必要です。</span><span class="sxs-lookup"><span data-stu-id="bd52b-116">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="bd52b-117">各ユーザーの ExchangeArchivingPolicy プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-117">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="bd52b-118">この手順は、Lync Server でのみ必要であり、Exchange は異なるフォレストに配置されています。</span><span class="sxs-lookup"><span data-stu-id="bd52b-118">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="bd52b-119">手順 1: Exchange のアーカイブを有効にする</span><span class="sxs-lookup"><span data-stu-id="bd52b-119">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="bd52b-120">Lync Server のアーカイブは、主にアーカイブ構成設定を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-120">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="bd52b-121">Lync Server 2013 をインストールすると、次の設定のグローバルコレクションが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-121">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="bd52b-122">(管理者は、必要に応じて、サイトのスコープでアーカイブ設定の新しいコレクションを作成することができます)。既定では、グローバル設定ではアーカイブが有効になっていません。また、これらの設定では Exchange アーカイブが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="bd52b-122">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="bd52b-123">Exchange アーカイブ管理者を使用するには、これらの構成設定で EnableArchiving と Enableexchangeアーカイブの両方のプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-123">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="bd52b-124">EnableArchiving プロパティは、次の3つの値のいずれかに設定できます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-124">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="bd52b-125">**なし**。</span><span class="sxs-lookup"><span data-stu-id="bd52b-125">**None**.</span></span> <span data-ttu-id="bd52b-126">アーカイブが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="bd52b-126">Archiving is disabled.</span></span> <span data-ttu-id="bd52b-127">これは既定の値です。</span><span class="sxs-lookup"><span data-stu-id="bd52b-127">This is the default value.</span></span> <span data-ttu-id="bd52b-128">EnableArchiving が None に設定されている場合、Lync Server アーカイブデータベースまたは Exchange 2013 には何もアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="bd52b-128">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="bd52b-129">**Imonly**。</span><span class="sxs-lookup"><span data-stu-id="bd52b-129">**ImOnly**.</span></span> <span data-ttu-id="bd52b-130">インスタントメッセージのトランスクリプトのみがアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-130">Only instant message transcripts are archived.</span></span> <span data-ttu-id="bd52b-131">Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-131">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="bd52b-132">Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-132">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="bd52b-133">**Imandwebconf**。</span><span class="sxs-lookup"><span data-stu-id="bd52b-133">**ImAndWebConf**.</span></span> <span data-ttu-id="bd52b-134">インスタントメッセージのトランスクリプトと Web 会議のトランスクリプトは両方ともアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-134">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="bd52b-135">Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-135">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="bd52b-136">Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-136">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="bd52b-137">EnableExchangeArchiving プロパティは、"EnableExchangeArchiving を True ($True)" に設定して Exchange アーカイブを有効にするか、EnableExchangeArchiving を False ($False) に設定して Exchange のアーカイブを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-137">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="bd52b-138">たとえば、次のコマンドを実行すると、インスタントメッセージのトランスクリプトがアーカイブされ、Exchange アーカイブも有効になります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-138">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="bd52b-139">Exchange アーカイブを無効にするには、次のようなコマンドを使用します。これにより、インスタントメッセージアーカイブは有効になりますが、Exchange へのアーカイブは無効になります (つまり、トランスクリプトは Lync Server にアーカイブされます)。</span><span class="sxs-lookup"><span data-stu-id="bd52b-139">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="bd52b-140">EnableArchiving プロパティが None に設定されている場合、Lync Server では、インスタントメッセージングと Web 会議のトランスクリプトはまったくアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="bd52b-140">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="bd52b-141">この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-141">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="bd52b-142">Exchange アーカイブは、Lync Server コントロールパネルを使用して有効 (または無効) にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-142">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="bd52b-143">この操作を行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-143">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="bd52b-144">コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-144">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="bd52b-145">[**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-145">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="bd52b-146">[**編集アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-146">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="bd52b-147">アーカイブする項目を選んだら、[ **Exchange Server 統合**] チェックボックスをオンにして、exchange アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-147">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="bd52b-148">Exchange のアーカイブを無効にするには、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-148">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd52b-149">[<STRONG>アーカイブ設定</STRONG>] が [<STRONG>アーカイブを無効にする</STRONG>] に設定されていると [<STRONG>Exchange Server の統合</STRONG>] チェック ボックスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="bd52b-149">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="bd52b-150">最初にアーカイブを有効にしてから、Exchange アーカイブを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-150">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="bd52b-151">Lync Server 2013 と Exchange 2013 が同じフォレストに配置されている場合、個々のユーザー (または少なくとも Exchange 2013 のメールアカウントを持つユーザー) のアーカイブは、Exchange のインプレースホールドポリシーを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-151">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="bd52b-152">以前のバージョンの Exchange を使用しているユーザーがいる場合、そのユーザーのアーカイブは Lync Server のアーカイブポリシーを使って管理されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-152">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="bd52b-153">Exchange 2013 上のアカウントを持つユーザーのみが、Lync のトランスクリプトを Exchange にアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-153">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="bd52b-154">Lync Server 2013 と Exchange 2013 が異なるフォレストに配置されている場合、個々のユーザー用のアーカイブは、個々のユーザーアカウントの ExchangeArchivingPolicy プロパティを構成することによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-154">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="bd52b-155">詳細については、手順3を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd52b-155">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="bd52b-156">手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする</span><span class="sxs-lookup"><span data-stu-id="bd52b-156">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="bd52b-157">アーカイブ (および Exchange のアーカイブ) を有効にした後、適切なアーカイブポリシーを変更して、ユーザーセッションが実際にアーカイブされることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-157">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="bd52b-158">アーカイブを有効にする (手順 1) と、Lync Server でインスタントメッセージングと Web 会議のトランスクリプトのアーカイブが開始されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bd52b-158">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="bd52b-159">このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-159">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="bd52b-160">Lync Server 2013 をインストールする場合は、次の2つのプロパティを含む単一のグローバルアーカイブポリシーもインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-160">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="bd52b-p119">**ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="bd52b-p120">**ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="bd52b-165">既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="bd52b-165">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="bd52b-166">グローバルポリシーを変更するには、Lync Server 管理シェルと CsArchivingPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-166">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="bd52b-167">次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-167">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="bd52b-p122">また、New-CsArchivingPolicy を使用して、サイト スコープまたはユーザーごとのスコープで新しいポリシーを作成することもできます。たとえば、次のコマンドを実行すると RedmondArchivingPolicy という名前の新しいユーザーごとのアーカイブ ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="bd52b-p123">ユーザーごとのポリシーを作成した場合は、そのポリシーを適切なユーザーに割り当てる必要があります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="bd52b-172">また、アーカイブポリシーは、Lync Server コントロールパネルを使用して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-172">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="bd52b-173">コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-173">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="bd52b-174">既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-174">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="bd52b-175">新しいアーカイブポリシーを作成するには、[**新規**] をクリックし、[**サイトポリシー** ] または [**ユーザーポリシー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-175">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="bd52b-176">新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-176">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="bd52b-177">手順 3: ExchangeArchivingPolicy プロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="bd52b-177">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="bd52b-178">Lync Server 2013 と Exchange 2013 が異なるフォレストにある場合は、アーカイブ構成設定で Exchange アーカイブを有効にするだけでは十分ではありません。これにより、インスタントメッセージと Web 会議のトランスクリプトは Exchange にアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="bd52b-178">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="bd52b-179">代わりに、関連する各 Lync Server ユーザーアカウントの ExchangeArchivingPolicy プロパティも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd52b-179">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="bd52b-180">このプロパティは、次の4つの値のいずれかに設定できます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-180">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="bd52b-181">Uninitialized: ユーザーの nm-exch-15-short メールボックスに対して構成されているインプレース保持設定に基づいてアーカイブが行われます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-181">Uninitialized.</span></span> <span data-ttu-id="bd52b-182">アーカイブが、ユーザーの Exchange メールボックスに対して構成されているインプレースホールド設定に基づいていることを示します。ユーザーのメールボックスでインプレース保持が有効になっていない場合、ユーザーは、そのユーザーのメッセージングと Web 会議の議事録を Lync Server にアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="bd52b-182">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="bd52b-183">**UseLyncArchivingPolicy**。</span><span class="sxs-lookup"><span data-stu-id="bd52b-183">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="bd52b-184">ユーザーのインスタントメッセージングと Web 会議のトランスクリプトを、Exchange ではなく Lync Server にアーカイブする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-184">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="bd52b-185">**Noarchiving**。</span><span class="sxs-lookup"><span data-stu-id="bd52b-185">**NoArchiving**.</span></span> <span data-ttu-id="bd52b-186">ユーザーのインスタントメッセージングと Web 会議のトランスクリプトがまったくアーカイブされないことを示します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-186">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="bd52b-187">この設定は、ユーザーに割り当てられている Lync Server アーカイブポリシーよりも優先されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bd52b-187">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="bd52b-188">**ArchivingToExchange**。</span><span class="sxs-lookup"><span data-stu-id="bd52b-188">**ArchivingToExchange**.</span></span> <span data-ttu-id="bd52b-189">ユーザーのインスタントメッセージングおよび Web 会議のトランスクリプトが、ユーザーのメールボックスに割り当てられている (または使用されていない) インプレースホールドの設定に関係なく、Exchange にアーカイブされることを示します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-189">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="bd52b-190">たとえば、インスタントメッセージングと Web 会議のトランスクリプトが常に Exchange にアーカイブされるようにユーザーアカウントを構成するには、次のようなコマンドを Lync Server 管理シェルから使うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-190">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="bd52b-191">ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd52b-191">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="bd52b-192">ExchangeArchivingPolicy プロパティの値を構成するためには、Lync Server 管理シェル (および Windows PowerShell) を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bd52b-192">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="bd52b-193">このプロパティは、Lync Server コントロールパネルの管理者には公開されません。</span><span class="sxs-lookup"><span data-stu-id="bd52b-193">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="bd52b-194">特定のアーカイブ ポリシーを割り当てられているすべてのユーザーの一覧を表示するには、次のようなコマンドを使用します。このコマンドを実行すると、ExchangeArchivingPolicy プロパティが Uninitialized に設定されているすべてのユーザーの Active Directory 表示名が取得されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-194">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="bd52b-195">同様に、次のコマンドを実行すると、ExchangeArchivingPolicy プロパティが UseLyncArchivingPolicy に設定されていないユーザーの表示名が取得されます。</span><span class="sxs-lookup"><span data-stu-id="bd52b-195">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

