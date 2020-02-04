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

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Microsoft Exchange Server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-24_

Microsoft Lync Server 2013 を使用すると、管理者は、インスタントメッセージと Web 会議のトランスクリプトを SQL Server データベースではなく、ユーザーの Microsoft Exchange Server 2013 メールボックスにアーカイブするオプションが提供されます。 管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。 Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。 このフォルダーは、エンドユーザーには表示されませんが、Exchange のメールボックス検索や Microsoft SharePoint Server 2013 を使用すると、フォルダーは Exchange 検索エンジンによってインデックス処理され、検出できます。 情報は、Exchange のインプレースホールド機能で使用されているものと同じフォルダー (メールのアーカイブおよびその他の Exchange 通信を担当します) に保存されているため、管理者は、1つのツールを使用してアーカイブされているすべての電子通信を検索することができます。ユーザーズ.

<div>


> [!IMPORTANT]  
> Lync の会話のアーカイブを完全に無効にするには、Lync の会話履歴も無効にする必要があります。 詳細については、次のトピックを参照してください。 <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Lync Server 2013 での内部および外部通信のアーカイブの管理</A>、<A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">新しい-csclientpolicy</A>、および<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set csclientpolicy</A>。



</div>

Exchange 2013 にトランスクリプトをアーカイブするには、最初に2つのサーバー間でサーバー間認証を構成する必要があります。 サーバー間認証が行われたら、Microsoft Lync Server 2013 で次のタスクを実行できます (ただし、セットアップと構成によっては、これらのすべてのタスクを完了する必要がない場合があることに注意してください)。

1.  Lync Server のアーカイブ構成設定を変更して、Exchange のアーカイブを有効にします。 この手順はすべての展開で必要です。

2.  ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。 この手順はすべての展開で必要です。

3.  各ユーザーの ExchangeArchivingPolicy プロパティを構成します。 この手順は、Lync Server でのみ必要であり、Exchange は異なるフォレストに配置されています。

<div>

## <a name="step-1-enabling-exchange-archiving"></a>手順 1: Exchange のアーカイブを有効にする

Lync Server のアーカイブは、主にアーカイブ構成設定を使用して管理されます。 Lync Server 2013 をインストールすると、次の設定のグローバルコレクションが自動的に作成されます。 (管理者は、必要に応じて、サイトのスコープでアーカイブ設定の新しいコレクションを作成することができます)。既定では、グローバル設定ではアーカイブが有効になっていません。また、これらの設定では Exchange アーカイブが有効になっていません。 Exchange アーカイブ管理者を使用するには、これらの構成設定で EnableArchiving と Enableexchangeアーカイブの両方のプロパティを設定する必要があります。 EnableArchiving プロパティは、次の3つの値のいずれかに設定できます。

  - **なし**。 アーカイブが無効になっています。 これは既定の値です。 EnableArchiving が None に設定されている場合、Lync Server アーカイブデータベースまたは Exchange 2013 には何もアーカイブされません。

  - **Imonly**。 インスタントメッセージのトランスクリプトのみがアーカイブされます。 Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。 Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。

  - **Imandwebconf**。 インスタントメッセージのトランスクリプトと Web 会議のトランスクリプトは両方ともアーカイブされます。 Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。 Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。

EnableExchangeArchiving プロパティは、"EnableExchangeArchiving を True ($True)" に設定して Exchange アーカイブを有効にするか、EnableExchangeArchiving を False ($False) に設定して Exchange のアーカイブを無効にすることができます。 たとえば、次のコマンドを実行すると、インスタントメッセージのトランスクリプトがアーカイブされ、Exchange アーカイブも有効になります。

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Exchange アーカイブを無効にするには、次のようなコマンドを使用します。これにより、インスタントメッセージアーカイブは有効になりますが、Exchange へのアーカイブは無効になります (つまり、トランスクリプトは Lync Server にアーカイブされます)。

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> EnableArchiving プロパティが None に設定されている場合、Lync Server では、インスタントメッセージングと Web 会議のトランスクリプトはまったくアーカイブされません。 この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。



</div>

Exchange アーカイブは、Lync Server コントロールパネルを使用して有効 (または無効) にすることもできます。 この操作を行うには、次の手順を実行します。

1.  コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

2.  [**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。

3.  [**編集アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。

4.  アーカイブする項目を選んだら、[ **Exchange Server 統合**] チェックボックスをオンにして、exchange アーカイブを有効にします。 Exchange のアーカイブを無効にするには、このチェックボックスをオフにします。

<div>


> [!NOTE]  
> [<STRONG>アーカイブ設定</STRONG>] が [<STRONG>アーカイブを無効にする</STRONG>] に設定されていると [<STRONG>Exchange Server の統合</STRONG>] チェック ボックスは利用できません。 最初にアーカイブを有効にしてから、Exchange アーカイブを有効にする必要があります。



</div>

Lync Server 2013 と Exchange 2013 が同じフォレストに配置されている場合、個々のユーザー (または少なくとも Exchange 2013 のメールアカウントを持つユーザー) のアーカイブは、Exchange のインプレースホールドポリシーを使用して管理されます。 以前のバージョンの Exchange を使用しているユーザーがいる場合、そのユーザーのアーカイブは Lync Server のアーカイブポリシーを使って管理されます。 Exchange 2013 上のアカウントを持つユーザーのみが、Lync のトランスクリプトを Exchange にアーカイブすることができます。

Lync Server 2013 と Exchange 2013 が異なるフォレストに配置されている場合、個々のユーザー用のアーカイブは、個々のユーザーアカウントの ExchangeArchivingPolicy プロパティを構成することによって管理されます。 詳細については、手順3を参照してください。

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする

アーカイブ (および Exchange のアーカイブ) を有効にした後、適切なアーカイブポリシーを変更して、ユーザーセッションが実際にアーカイブされることを確認する必要があります。 アーカイブを有効にする (手順 1) と、Lync Server でインスタントメッセージングと Web 会議のトランスクリプトのアーカイブが開始されないことに注意してください。 このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。 Lync Server 2013 をインストールする場合は、次の2つのプロパティを含む単一のグローバルアーカイブポリシーもインストールします。

  - **ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。

  - **ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。

既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。 グローバルポリシーを変更するには、Lync Server 管理シェルと CsArchivingPolicy コマンドレットを使用します。 次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

また、New-CsArchivingPolicy を使用して、サイト スコープまたはユーザーごとのスコープで新しいポリシーを作成することもできます。たとえば、次のコマンドを実行すると RedmondArchivingPolicy という名前の新しいユーザーごとのアーカイブ ポリシーが作成されます。

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

ユーザーごとのポリシーを作成した場合は、そのポリシーを適切なユーザーに割り当てる必要があります。次に例を示します。

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

また、アーカイブポリシーは、Lync Server コントロールパネルを使用して管理することもできます。 コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。 既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。 新しいアーカイブポリシーを作成するには、[**新規**] をクリックし、[**サイトポリシー** ] または [**ユーザーポリシー**] を選びます。 新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>手順 3: ExchangeArchivingPolicy プロパティを構成する

Lync Server 2013 と Exchange 2013 が異なるフォレストにある場合は、アーカイブ構成設定で Exchange アーカイブを有効にするだけでは十分ではありません。これにより、インスタントメッセージと Web 会議のトランスクリプトは Exchange にアーカイブされません。 代わりに、関連する各 Lync Server ユーザーアカウントの ExchangeArchivingPolicy プロパティも構成する必要があります。 このプロパティは、次の4つの値のいずれかに設定できます。

1.  Uninitialized: ユーザーの nm-exch-15-short メールボックスに対して構成されているインプレース保持設定に基づいてアーカイブが行われます。 アーカイブが、ユーザーの Exchange メールボックスに対して構成されているインプレースホールド設定に基づいていることを示します。ユーザーのメールボックスでインプレース保持が有効になっていない場合、ユーザーは、そのユーザーのメッセージングと Web 会議の議事録を Lync Server にアーカイブします。

2.  **UseLyncArchivingPolicy**。 ユーザーのインスタントメッセージングと Web 会議のトランスクリプトを、Exchange ではなく Lync Server にアーカイブする必要があることを示します。

3.  **Noarchiving**。 ユーザーのインスタントメッセージングと Web 会議のトランスクリプトがまったくアーカイブされないことを示します。 この設定は、ユーザーに割り当てられている Lync Server アーカイブポリシーよりも優先されることに注意してください。

4.  **ArchivingToExchange**。 ユーザーのインスタントメッセージングおよび Web 会議のトランスクリプトが、ユーザーのメールボックスに割り当てられている (または使用されていない) インプレースホールドの設定に関係なく、Exchange にアーカイブされることを示します。

たとえば、インスタントメッセージングと Web 会議のトランスクリプトが常に Exchange にアーカイブされるようにユーザーアカウントを構成するには、次のようなコマンドを Lync Server 管理シェルから使うことができます。

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

ExchangeArchivingPolicy プロパティの値を構成するためには、Lync Server 管理シェル (および Windows PowerShell) を使用する必要があることに注意してください。 このプロパティは、Lync Server コントロールパネルの管理者には公開されません。

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

