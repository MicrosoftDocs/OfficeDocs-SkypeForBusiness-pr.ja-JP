---
title: 'Lync Server 2013: ユーザー アカウント設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b74056587a192ec81f0dffb0044fb76e7698960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="bac34-102">Lync Server 2013 でのユーザー アカウント設定の構成</span><span class="sxs-lookup"><span data-stu-id="bac34-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bac34-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="bac34-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="bac34-104">ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="bac34-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="bac34-105">認証には、Lync Server のユーザーアカウントで指定されたテレフォニー**回線 URI**が必要です。</span><span class="sxs-lookup"><span data-stu-id="bac34-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="bac34-106">このトピックの手順は、[**回線 URI**] を 1 つのユーザー アカウントに対して割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bac34-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="bac34-107">[**回線 URI**] を複数のユーザー アカウントに対して割り当てる必要がある場合は、**Set-CsUser** コマンドレットを使用するスクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bac34-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="bac34-108">サンプルスクリプトを使用して複数のユーザーアカウントに**行の uri**を割り当てる方法の詳細については、の「 [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)複数のユーザーに行の uri を割り当てる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac34-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="bac34-109">ユーザーアカウント設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="bac34-109">To configure user account settings</span></span>

1.  <span data-ttu-id="bac34-110">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bac34-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="bac34-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bac34-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bac34-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bac34-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bac34-113">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac34-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="bac34-114">検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、[**フィルターの追加**] をクリックして検索フィールドを指定し、次に [**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac34-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="bac34-115">ユーザー名をダブルクリックして、[ **Lync Server ユーザーの編集**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="bac34-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="bac34-116">[**テレフォニー**] の下の [**回線 URI**] フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。</span><span class="sxs-lookup"><span data-stu-id="bac34-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bac34-117">[<STRONG>回線 URI</STRONG>] を指定できるのは、[<STRONG>テレフォニー</STRONG>] が [<STRONG>PC 間のみ</STRONG>]、[<STRONG>エンタープライズ VoIP</STRONG>]、[<STRONG>リモート通話コントロール</STRONG>]、または [<STRONG>リモート通話コントロールのみ</STRONG>] に設定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="bac34-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="bac34-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac34-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

