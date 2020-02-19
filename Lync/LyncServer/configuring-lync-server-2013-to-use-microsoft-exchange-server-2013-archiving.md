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
ms.openlocfilehash: 5a7f331cfa79472db187f30b626baad9655f2a7b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Microsoft Exchange Server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-24_

Microsoft Lync Server 2013 を使用すると、管理者は、インスタントメッセージングと Web 会議のトランスクリプトを SQL Server データベースではなく、ユーザーの Microsoft Exchange Server 2013 メールボックスにアーカイブすることができます。 管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。 Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。 このフォルダーはエンドユーザーには表示されませんが、フォルダーは Exchange 検索エンジンによってインデックスが作成され、Exchange メールボックスの検索や Microsoft SharePoint Server 2013 を使用して検出できます。 情報は、Exchange のインプレース保持機能 (メールのアーカイブとその他の Exchange 通信を担当する) で使用されるものと同じフォルダーに格納されているため、管理者は1つのツールを使用してアーカイブされたすべての電子通信を検索できます。マニュアル.

<div>


> [!IMPORTANT]  
> Lync 会話のアーカイブを完全に無効にするには、Lync 会話履歴も無効にする必要があります。 詳細については、以下のトピックを参照してください。 Lync Server 2013、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>、および<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-csclientpolicy</A><A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">で、内部通信と外部通信のアーカイブを管理</A>する。



</div>

Exchange 2013 にトランスクリプトをアーカイブするには、2つのサーバー間でサーバー間認証を構成することから始める必要があります。 サーバー間認証が行われた後、Microsoft Lync Server 2013 で次のタスクを実行できます (セットアップと構成によっては、これらのタスクをすべて完了する必要がない場合があることに注意してください)。

1.  Lync Server アーカイブ構成設定を変更して、Exchange アーカイブを有効にします。 この手順はすべての展開で必要です。

2.  ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。 この手順はすべての展開で必要です。

3.  各ユーザーの ExchangeArchivingPolicy プロパティを構成します。 この手順は、Lync Server でのみ必要であり、Exchange が異なるフォレストに配置されています。

<div>

## <a name="step-1-enabling-exchange-archiving"></a>手順 1: Exchange アーカイブを有効にする

Lync Server でのアーカイブは、主にアーカイブ構成設定を使用して管理されます。 Lync Server 2013 をインストールすると、これらの設定の単一のグローバルコレクションが自動的に割り当てられます。 (必要に応じて、管理者はサイトスコープでアーカイブ設定の新しいコレクションを作成できます)。既定では、グローバル設定でアーカイブが有効になっていません。また、これらの設定では Exchange アーカイブが有効になっていません。 Exchange アーカイブ管理者を使用するには、これらの構成設定で EnableArchiving と Enableexchangeアーカイビングプロパティの両方を構成する必要があります。 EnableArchiving プロパティには、次の3つの値のいずれかを設定できます。

  - **なし**。 アーカイブが無効になっています。 これは既定の値です。 EnableArchiving が [なし] に設定されている場合は、Lync Server アーカイブデータベースまたは Exchange 2013 のいずれかにアーカイブされません。

  - **Imonly**。 インスタントメッセージのトランスクリプトのみがアーカイブされます。 Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。 Exchange のアーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。

  - **Imandwebconf**。 インスタントメッセージのトランスクリプトと Web 会議のトランスクリプトは、両方ともアーカイブされます。 Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。 Exchange のアーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。

EnableExchangeArchiving プロパティは、ブール値です。 EnableExchangeArchiving を True ($True) に設定して、Exchange アーカイブを有効にするか、EnableExchangeArchiving を False ($False) に設定して Exchange アーカイブを無効にします。 たとえば、次のコマンドを実行すると、インスタントメッセージングトランスクリプトのアーカイブが有効になり、Exchange アーカイブも有効になります。

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Exchange アーカイブを無効にするには、次のようなコマンドを使用します。これにより、インスタントメッセージングアーカイブは有効になりますが、Exchange へのアーカイブが無効になります (つまり、トランスクリプトは Lync Server にアーカイブされます)。

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> EnableArchiving プロパティが None に設定されている場合、Lync Server はインスタントメッセージングと Web 会議のトランスクリプトをまったくアーカイブしません。 この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。



</div>

Exchange アーカイブは、Lync Server コントロールパネルを使用して有効または無効にすることもできます。 これを行うには、次の手順を実行します。

1.  コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

2.  [**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。

3.  [**編集 アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。

4.  アーカイブするアイテムを選択した後、[ **Exchange Server 統合**] チェックボックスをオンにして、exchange アーカイブを有効にします。 Exchange アーカイブを無効にするには、このチェックボックスをオフにします。

<div>


> [!NOTE]  
> [<STRONG>アーカイブ設定</STRONG>] が [<STRONG>アーカイブを無効にする</STRONG>] に設定されていると [<STRONG>Exchange Server の統合</STRONG>] チェック ボックスは利用できません。 最初にアーカイブを有効にしてから、Exchange アーカイブを有効にする必要があります。



</div>

Lync Server 2013 と Exchange 2013 が同じフォレストに存在する場合、個々のユーザー (または少なくとも Exchange 2013 の電子メールアカウントを持つユーザー) のアーカイブは、Exchange のインプレース保持ポリシーを使用して管理されます。 以前のバージョンの Exchange に所属しているユーザーがいる場合は、それらのユーザーのアーカイブが Lync Server アーカイブポリシーを使用して管理されます。 Exchange 2013 上のアカウントを持つユーザーのみが、Lync トランスクリプトを Exchange にアーカイブできることに注意してください。

Lync Server 2013 と Exchange 2013 が異なるフォレストに配置されている場合は、個々のユーザーアカウントの ExchangeArchivingPolicy プロパティを構成することによって、個々のユーザーのアーカイブを管理できます。 詳細については、手順3を参照してください。

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする

アーカイブ (および Exchange アーカイブ) を有効にした後、適切なアーカイブポリシーを変更して、ユーザーセッションが実際にアーカイブされるようにする必要があります。 アーカイブを有効にする (手順 1) だけでは、Lync Server でインスタントメッセージングと Web 会議のトランスクリプトのアーカイブが開始されることはありません。 このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。 Lync Server 2013 をインストールするときは、次の2つのプロパティを含む単一のグローバルなアーカイブポリシーもインストールします。

  - **ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。

  - **ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。

既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。 グローバルポリシーを変更するには、Lync Server 管理シェルと Grant-csarchivingpolicy コマンドレットを使用できます。 次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

また、New-CsArchivingPolicy を使用して、サイト スコープまたはユーザーごとのスコープで新しいポリシーを作成することもできます。たとえば、次のコマンドを実行すると RedmondArchivingPolicy という名前の新しいユーザーごとのアーカイブ ポリシーが作成されます。

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

ユーザーごとのポリシーを作成した場合は、そのポリシーを適切なユーザーに割り当てる必要があります。次に例を示します。

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

また、アーカイブポリシーは、Lync Server コントロールパネルを使用して管理することもできます。 コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。 既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。 新しいアーカイブポリシーを作成するには、[**新規**] をクリックし、[**サイトポリシー** ] または [**ユーザーポリシー**] を選択します。 新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>手順 3: ExchangeArchivingPolicy プロパティを構成する

Lync Server 2013 と Exchange 2013 が異なるフォレストに配置されている場合は、アーカイブ構成設定で Exchange アーカイブを有効にできるだけではありません。これにより、インスタントメッセージングと Web 会議のトランスクリプトは Exchange にアーカイブされません。 代わりに、各関連する Lync Server ユーザーアカウントで ExchangeArchivingPolicy プロパティを構成する必要もあります。 このプロパティには、次の4つの値のいずれかを設定できます。

1.  ない. アーカイブが、ユーザーの Exchange メールボックスに対して構成されたインプレース保持の設定に基づいて行われることを示します。ユーザーのメールボックスでインプレースホールドが有効になっていない場合、ユーザーには、そのユーザーのメッセージングと Web 会議のトランスクリプトが Lync Server にアーカイブされます。

2.  **UseLyncArchivingPolicy**。 ユーザーのインスタントメッセージングおよび Web 会議のトランスクリプトを Exchange ではなく Lync Server にアーカイブする必要があることを示します。

3.  **Noarchiving**。 ユーザーのインスタントメッセージングと Web 会議のトランスクリプトをまったくアーカイブしないことを示します。 この設定は、ユーザーに割り当てられた Lync Server アーカイブポリシーよりも優先されることに注意してください。

4.  **ArchivingToExchange**。 ユーザーのメールボックスに割り当てられている (またはしていない) インプレース保持の設定に関係なく、ユーザーのインスタントメッセージングおよび Web 会議のトランスクリプトを Exchange にアーカイブする必要があることを示します。

たとえば、インスタントメッセージングと Web 会議のトランスクリプトを常に Exchange にアーカイブするようにユーザーアカウントを構成するには、Lync Server 管理シェルから次のようなコマンドを使用できます。

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

ExchangeArchivingPolicy プロパティの値を構成するには、Lync Server 管理シェル (および Windows PowerShell) を使用する必要があることに注意してください。 このプロパティは、Lync Server コントロールパネルの管理者には公開されません。

特定のアーカイブ ポリシーを割り当てられているすべてのユーザーの一覧を表示するには、次のようなコマンドを使用します。このコマンドを実行すると、ExchangeArchivingPolicy プロパティが Uninitialized に設定されているすべてのユーザーの Active Directory 表示名が取得されます。

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

同様に、次のコマンドを実行すると、ExchangeArchivingPolicy プロパティが UseLyncArchivingPolicy に設定されていないユーザーの表示名が取得されます。

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

