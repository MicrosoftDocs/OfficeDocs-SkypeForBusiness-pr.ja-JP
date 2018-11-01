---
title: Microsoft Exchange Server 2013 アーカイブを使用するための Lync Server 2013 の構成
TOCTitle: Exchange Server 2013 アーカイブを使用するための Lync Server 2013 の構成
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49886880
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Exchange Server 2013 アーカイブを使用するための Microsoft Lync Server 2013 の構成

 

_**トピックの最終更新日:** 2014-06-24_

Microsoft Lync Server 2013 には、インスタント メッセージングと Web 会議のトランスクリプトを SQL Server データベースではなくユーザーの Microsoft Exchange Server 2013 メールボックスにアーカイブするオプションが用意されています。管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。このフォルダーはエンドユーザーからは見えませんが、Exchange 検索エンジンによってフォルダーのインデックスが作成されており、Exchange メールボックス検索や Microsoft SharePoint Server 2013 を使用して検出できます。Exchange インプレース保持機能 (電子メールやその他の Exchange の通信をアーカイブする働きをする) で使用されるフォルダーと同じフォルダーに情報が格納されるので、管理者はユーザー用にアーカイブされたすべての電子通信を 1 つのツールで検索できます。


> [!IMPORTANT]
> Lync 会話のアーカイブを完全に無効にするには、Lync 会話の履歴も無効にする必要があります。詳細については、「<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Lync Server 2013 での内部通信および外部通信のアーカイブの管理</A>」、「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>」、および「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>」のトピックを参照してください。



トランスクリプトを Exchange 2013 にアーカイブするには、まず 2 つのサーバーの間でサーバー間認証を構成する必要があります。サーバー間認証の準備ができたら、次に Microsoft Lync Server 2013 で以下のタスクを実行します (使用中の設定と構成によっては、タスクをすべて実行する必要がない場合があります)。

1.  Lync Server のアーカイブ構成設定を変更して Exchange アーカイブを有効にします。この手順はすべての展開で必要です。

2.  ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。この手順はすべての展開で必要です。

3.  各ユーザーの ExchangeArchivingPolicy プロパティを構成します。この手順は、Lync Server と Exchange が異なるフォレストにある場合にのみ必要です。

## 手順 1: Exchange アーカイブを有効にする

Lync Server のアーカイブは、主にアーカイブ構成設定を使用して管理します。Lync Server 2013 のインストール時に、アーカイブ構成設定の単一のグローバル コレクションが自動的に作成されます (管理者は必要に応じてアーカイブ設定の新しいコレクションをサイト スコープで作成できます)。既定では、グローバル設定でアーカイブは有効になっておらず、Exchange アーカイブも有効になっていません。Exchange アーカイブを使用するには、これらの構成設定で EnableArchiving プロパティと EnableExchangeArchiving プロパティの両方を構成する必要があります。EnableArchiving プロパティは、次の 3 つのいずれかの値に設定できます。

  - **None** : アーカイブは無効になります。これが既定値です。EnableArchiving を None に設定した場合、Lync Server アーカイブ データベースにも Exchange 2013 にも何もアーカイブされません。

  - **ImOnly** : インスタント メッセージのトランスクリプトのみがアーカイブされます。Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。

  - **ImAndWebConf** : インスタント メッセージのトランスクリプトと Web 会議のトランスクリプトの両方がアーカイブされます。Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange 2013 にアーカイブされます。Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Lync Server にアーカイブされます。

EnableExchangeArchiving プロパティはブール値です。EnableExchangeArchiving を True ($True) に設定すると Exchange アーカイブが有効になり、EnableExchangeArchiving を False ($False) に設定すると Exchange アーカイブが無効になります。たとえば、次のコマンドを実行するとインスタント メッセージングのトランスクリプトのアーカイブが有効になり、同時に Exchange アーカイブも有効になります。

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Exchange アーカイブを無効にするには、次のようなコマンドを使用します。このコマンドを実行するとインスタント メッセージングのアーカイブは有効になりますが、Exchange へのアーカイブは無効になります (言い換えると、トランスクリプトは Lync Server にアーカイブされます)。

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

> [!NOTE]
> EnableArchiving プロパティが None に設定されている場合、Lync Server はインスタント メッセージングのトランスクリプトも Web 会議のトランスクリプトも一切アーカイブしません。この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。


また、Lync Server コントロール パネルを使用して Exchange アーカイブを有効 (または無効) にすることもできます。これを行うには、次の手順を実行します。

1.  コントロール パネルで、\[**監視およびアーカイブ**\] をクリックし、\[**アーカイブ構成**\] をクリックします。

2.  \[**アーカイブ構成**\] タブで、変更するアーカイブ設定のコレクション (\[**グローバル**\] コレクションなど) をダブルクリックします。

3.  \[**編集アーカイブ設定**\] ウィンドウで、\[**アーカイブ設定**\] ドロップダウン リストをクリックし、\[**IM セッションをアーカイブする**\] (インスタント メッセージング セッションのみをアーカイブする場合) または \[**IM および Web 会議セッションをアーカイブする**\] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。

4.  アーカイブするアイテムを選択したら、\[**Exchange Server の統合**\] チェック ボックスをオンにして Exchange アーカイブを有効にします。Exchange アーカイブを無効にするには、このチェック ボックスをオフにします。

> [!NOTE]
> [<strong>アーカイブ設定</strong>] が [<strong>アーカイブを無効にする</strong>] に設定されていると [<strong>Exchange Server の統合</strong>] チェック ボックスは利用できません。まずアーカイブを有効にしてから Exchange アーカイブを有効にする必要があります。


Lync Server 2013 と Exchange 2013 が同じフォレストにある場合、個々のユーザー (または少なくとも Exchange 2013 に電子メール アカウントを持つユーザー) のアーカイブは Exchange インプレース保持ポリシーを使用して管理されます。以前のバージョンの Exchange に所属するユーザーがいる場合、それらのユーザーのアーカイブは Lync Server アーカイブ ポリシーを使用して管理されます。Lync のトランスクリプトを Exchange にアーカイブできるのは、Exchange 2013 にアカウントを持つユーザーだけです。

Lync Server 2013 と Exchange 2013 が異なるフォレストにある場合、個々のユーザーのアーカイブは、ユーザー アカウントごとに ExchangeArchivingPolicy プロパティを構成して管理します。詳細については、手順 3. を参照してください。

## 手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする

アーカイブ (および Exchange アーカイブ) を有効にした後は、適切なアーカイブ ポリシーを変更して、ユーザー セッションが実際にアーカイブされるようにする必要があります。単にアーカイブを有効にしただけでは (手順 1.)、Lync Server はインスタント メッセージングと Web 会議のトランスクリプトのアーカイブを開始しません。このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。Lync Server 2013 をインストールすると、次の 2 つのプロパティを含む単一のグローバルなアーカイブ ポリシーもインストールされます。

  - **ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。

  - **ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。

既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。グローバル ポリシーを変更するには、Lync Server 管理シェルと Set-CsArchivingPolicy コマンドレットを使用します。次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

また、New-CsArchivingPolicy を使用して、サイト スコープまたはユーザーごとのスコープで新しいポリシーを作成することもできます。たとえば、次のコマンドを実行すると RedmondArchivingPolicy という名前の新しいユーザーごとのアーカイブ ポリシーが作成されます。

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

ユーザーごとのポリシーを作成した場合は、そのポリシーを適切なユーザーに割り当てる必要があります。次に例を示します。

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

また、Lync Server コントロール パネルを使用してアーカイブ ポリシーを管理することもできます。コントロール パネル内で、\[**監視およびアーカイブ**\] をクリックし、\[**アーカイブ ポリシー**\] をクリックします。既存のポリシーを変更するには、ポリシー (\[グローバル\] など) をダブルクリックし、\[**アーカイブ ポリシーの編集**\] ウィンドウで、\[**内部通信をアーカイブする**\] および \[**外部通信をアーカイブする**\] チェック ボックスを必要に応じてオンまたはオフにします。新しいアーカイブ ポリシーを作成するには、\[**新規**\] をクリックし、\[**サイト ポリシー**\] または \[**ユーザー ポリシー**\] を選択します。新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに (\[**ユーザー**\] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。

## 手順 3: ExchangeArchivingPolicy プロパティを構成する

Lync Server 2013 と Exchange 2013 が異なるフォレストにある場合は、単にアーカイブ構成設定で Exchange アーカイブを有効にするだけでは不十分です。それだけではインスタント メッセージングのトランスクリプトも Web 会議のトランスクリプトも Exchange にアーカイブされません。この場合は、関連する各 Lync Server ユーザー アカウントで ExchangeArchivingPolicy プロパティも構成する必要があります。このプロパティは、次の 4 つのいずれかの値に設定できます。

1.  Uninitialized: ユーザーの Exchange メールボックスに対して構成されているインプレース保持設定に基づいてアーカイブが行われます。ユーザーのメールボックスでインプレース保持が有効になっていない場合、ユーザーのインスタント メッセージングおよび Web 会議のトランスクリプトは Lync Server にアーカイブされます。

2.  **UseLyncArchivingPolicy**: ユーザーのインスタント メッセージングおよび Web 会議のトランスクリプトは Exchange ではなく Lync Server にアーカイブされます。

3.  **NoArchiving**: ユーザーのインスタント メッセージングおよび Web 会議のトランスクリプトは一切アーカイブされません。この設定はユーザーに割り当てられたあらゆる Lync Server アーカイブ ポリシーに優先することに注意してください。

4.  **ArchivingToExchange** : ユーザーのインスタント メッセージングおよび Web 会議のトランスクリプトは、ユーザーのメールボックスに割り当てられている (または割り当てられていない) インプレース保持設定にかかわらず Exchange にアーカイブされます。

たとえば、インスタント メッセージングおよび Web 会議のトランスクリプトが常に Exchange にアーカイブされるようにユーザー アカウントを構成するには、Lync Server 管理シェルから次のようなコマンドを使用します。

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

ExchangeArchivingPolicy プロパティの値を構成するには、Lync Server 管理シェル (および Windows PowerShell) を使用する必要があります。Lync Server コントロール パネルで管理者がこのプロパティを操作することはできません。

特定のアーカイブ ポリシーを割り当てられているすべてのユーザーの一覧を表示するには、次のようなコマンドを使用します。このコマンドを実行すると、ExchangeArchivingPolicy プロパティが Uninitialized に設定されているすべてのユーザーの Active Directory 表示名が取得されます。

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

同様に、次のコマンドを実行すると、ExchangeArchivingPolicy プロパティが UseLyncArchivingPolicy に設定されていないユーザーの表示名が取得されます。

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

