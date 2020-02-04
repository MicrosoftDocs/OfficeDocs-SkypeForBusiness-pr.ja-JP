---
title: 'Lync Server 2013: カテゴリの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf7b7b3ceb24e3b5bffb307cdde048e7a0cabb8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="88ed7-102">Lync Server 2013 でのカテゴリの構成</span><span class="sxs-lookup"><span data-stu-id="88ed7-102">Configure categories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88ed7-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="88ed7-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="88ed7-104">Lync Server 2013 コントロールパネルで、[**常設チャット**] ページの [**カテゴリ**] セクションを使ってカテゴリを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="88ed7-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="88ed7-105">常設チャットルームカテゴリは、チャットルームを整理するための論理的な構造です。</span><span class="sxs-lookup"><span data-stu-id="88ed7-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="88ed7-106">カテゴリは、チャット ルームの作成やチャット ルームへの参加を許可するユーザーとユーザー グループを制御するアクセス制御リスト (ACL) の既定のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="88ed7-107">カテゴリを使用して、組織内の異なる部門間に倫理的境界を設置できます。</span><span class="sxs-lookup"><span data-stu-id="88ed7-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="88ed7-108">チャットルームのカテゴリには、チャットルームを含めることができますが、他のカテゴリを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="88ed7-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="88ed7-109">各カテゴリでは、[名前]、[説明] などのメタデータを使用してカテゴリの内容が記述されます。</span><span class="sxs-lookup"><span data-stu-id="88ed7-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="88ed7-110">さらに、このカテゴリにはプロパティがあり、チャットルームで招待またはファイルのアップロードが許可されているか、チャット履歴が含まれているかなど、チャットルームの動作を制御するために設定できます。</span><span class="sxs-lookup"><span data-stu-id="88ed7-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="88ed7-111">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="88ed7-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="88ed7-112">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="88ed7-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88ed7-113">[**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="88ed7-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88ed7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="88ed7-115">Windows PowerShell コマンドレットを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="88ed7-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="88ed7-116">詳細については、展開ドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88ed7-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="88ed7-117">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88ed7-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="88ed7-118">複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="88ed7-119">[**カテゴリ**] ページで、[**新規**] または [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88ed7-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="88ed7-120">[**サービスの選択**] で、カテゴリの作成が必要な常設チャットサーバープールに対応するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="88ed7-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="88ed7-121">[サービス] は、カテゴリが属しているプールを特定するために常設チャット (クライアント) で使用される常設チャットサーバープールです。</span><span class="sxs-lookup"><span data-stu-id="88ed7-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="88ed7-122">カテゴリは、1つの常設チャットサーバープールにのみ属すことができ、別のプールに移動したり、別のプールで共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="88ed7-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="88ed7-123">[**新しいカテゴリ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="88ed7-124">[**名前**] に、新しいルーム カテゴリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="88ed7-125">[**説明**] に、ルーム カテゴリの詳細を指定します (たとえば「Contoso 用のカテゴリ」と指定します)。</span><span class="sxs-lookup"><span data-stu-id="88ed7-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="88ed7-126">このカテゴリに属するチャットルームに対して招待を有効にできるかどうかを制御するには、[**招待を有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="88ed7-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="88ed7-127">選択されている場合、このカテゴリの会議室の出席依頼のオンとオフを切り替えることができます。この設定をオフにすると、このカテゴリのルームに招待状は許可されません。</span><span class="sxs-lookup"><span data-stu-id="88ed7-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="88ed7-128">会議室が招待されている場合、会議室に新しいメンバーが追加されると、そのユーザーは、常設チャットクライアントで新しい会議室の通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="88ed7-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="88ed7-p107">このカテゴリに属するチャット ルームでファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合、このカテゴリのルームでは、ファイルのアップロードを有効または無効にできます。オフにした場合、このカテゴリのルームではファイルのアップロードは許可されません。</span><span class="sxs-lookup"><span data-stu-id="88ed7-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="88ed7-131">この設定は、Office Communications Server 2007 R2&nbsp;グループチャットサーバーまたは Lync server 2010 を使っているカスタムアプリケーションまたは以前のグループチャットクライアントで、グループチャットで会議室にファイルを投稿できます。</span><span class="sxs-lookup"><span data-stu-id="88ed7-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="88ed7-132">Lync 2013 クライアントには、ファイルのアップロード/ダウンロード機能がありません。そのため、Lync 2013 の展開または Lync 2013 クライアントが純粋にインストールされている場合は、常設チャットサーバーのチャットルームにファイルを投稿することはできません。</span><span class="sxs-lookup"><span data-stu-id="88ed7-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="88ed7-133">チャット履歴を管理するには、[**チャット履歴を有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="88ed7-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="88ed7-134">選択されている場合、ルームチャットは永続的になります。それ以外の場合は、チャットメッセージは保持されません。</span><span class="sxs-lookup"><span data-stu-id="88ed7-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="88ed7-135">コンプライアンスが有効になっている場合、ルームのチャットはコンプライアンスに保存されますが、ユーザーは古いメッセージにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="88ed7-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="88ed7-136">このオプションは、チャット履歴を保持する必要のないリアルタイムの共同作業用に指定された会議室に使用できます。</span><span class="sxs-lookup"><span data-stu-id="88ed7-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="88ed7-137">[**カテゴリの編集**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="88ed7-138">[許可された**メンバー** ] セクションの [**メンバーシップ**] で、カテゴリに属するチャットルームのメンバーとして追加することを許可されているユーザーおよびその他の Active Directory ドメインサービスプリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="88ed7-139">カテゴリで許可されているプリンシパルは、カテゴリ内のルームを検索することができます (ルームが非表示になっている場合を除き、ルームのメンバーだけがディレクトリ内で検索できます)。</span><span class="sxs-lookup"><span data-stu-id="88ed7-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="88ed7-140">[**メンバーシップ**] の [**拒否するメンバー** ] セクションで、会議室から拒否されているメンバーに関連付けられているユーザーおよびその他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="88ed7-141">[**メンバーシップ**] の [作成**者] セクション**で、カテゴリの作成者に関連付けられているユーザーおよびその他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="88ed7-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="88ed7-142">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="88ed7-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="88ed7-143">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88ed7-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

