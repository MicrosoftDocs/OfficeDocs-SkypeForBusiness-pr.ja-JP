---
title: Skype for Business Server でアーカイブを使用Exchange Server構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: '概要: 2016 年または 2016 年Exchange Server 2013 年Exchange Server Skype for Business Server の IM トランスクリプトを構成します。'
ms.openlocfilehash: 43a57fc227f7fc0dbcb33b2ecb4808f3e9762ad6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120316"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Skype for Business Server でアーカイブを使用Exchange Server構成する

**概要:** 2016 または 2016 Exchange Server 2013 Exchange Server Skype for Business Server の IM トランスクリプトを構成します。

Skype for Business Server を使用すると、管理者は、SQL Server データベースではなく、ユーザーの Exchange Server 2016 または Exchange Server 2013 メールボックスにインスタント メッセージングと Web 会議のトランスクリプトをアーカイブできます。 管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。 Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。 このフォルダーはエンド ユーザーには表示されませんが、フォルダーは Exchange 検索エンジンによってインデックス付けされ、Exchange メールボックス検索または Microsoft SharePoint Server 2013 を使用して検出できます。 情報は Exchange In-Place 保留機能 (電子メールや他の Exchange 通信のアーカイブを担当) で使用される同じフォルダーに格納されますので、管理者は 1 つのツールを使用して、ユーザー用にアーカイブされた電子通信を検索できます。

> [!IMPORTANT]
> 会話のアーカイブを完全に無効にするには、会話履歴も無効にする必要があります。 詳細については[、「Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications)での内部および外部通信のアーカイブの管理」、New-CsClientPolicy、および[Set-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)を参照してください。 [](/powershell/module/skype/set-csclientpolicy?view=skype-ps)

トランスクリプトをサーバーにアーカイブするには、Exchange Server Skype for Business Server とサーバー間のサーバー間認証を構成する必要Exchange Server。 サーバー間認証が実行された後、Skype for Business Server で次のタスクを実行できます (セットアップと構成によっては、これらのタスクの一部を完了する必要が生じない場合があります)。

1. Skype for Business Server のアーカイブ構成設定を変更して Exchange アーカイブを有効にします。 この手順はすべての展開で必要です。

2. ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。 この手順はすべての展開で必要です。

3. 各ユーザーの ExchangeArchivingPolicy プロパティを構成します。 この手順が必要になるのは、Skype for Business Server と Exchange Server別のフォレストにある場合のみです。

## <a name="step-1-enabling-exchange-archiving"></a>手順 1: Exchange アーカイブを有効にする

Skype for Business Server でのアーカイブは、主にアーカイブ構成設定を使用して管理されます。 Skype for Business Server をインストールすると、これらの設定の単一のグローバル コレクションが自動的に与えられる。 (管理者は、必要に応じて、サイト スコープでアーカイブ設定の新しいコレクションを作成できます)。既定では、グローバル設定ではアーカイブは有効ではなく、これらの設定では Exchange アーカイブが有効になっていません。 Exchange アーカイブを使用するには、管理者は、これらの構成設定で EnableArchiving プロパティと EnableExchangeArchiving プロパティの両方を構成する必要があります。 EnableArchiving プロパティは、次の 3 つの値のいずれかを設定できます。

- **なし 。** アーカイブは無効です。 これは既定の値です。 EnableArchiving が None に設定されている場合、Skype for Business Server アーカイブ データベースまたは Skype のアーカイブ データベースに何もアーカイブExchange Server。

- **ImOnly**. インスタント メッセージトランスクリプトだけがアーカイブされます。 Exchange のアーカイブが有効になっている場合、これらのトランスクリプトは、そのドキュメントにアーカイブExchange Server。 Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Skype for Business Server にアーカイブされます。

- **ImAndWebConf**. インスタント メッセージトランスクリプトと Web 会議トランスクリプトの両方がアーカイブされます。 Exchange のアーカイブが有効になっている場合、これらのトランスクリプトは、このドキュメントにアーカイブExchange Server。 Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Skype for Business Server にアーカイブされます。

EnableExchangeArchiving プロパティはブール値です。EnableExchangeArchiving を True ($True) に設定して Exchange アーカイブを有効にするか、EnableExchangeArchiving を False ($False) に設定して Exchange アーカイブを無効にします。 たとえば、このコマンドを使用すると、インスタント メッセージング トランスクリプトのアーカイブが有効にされ、Exchange のアーカイブも有効にできます。

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Exchange アーカイブを無効にするには、次のようなコマンドを使用します。このコマンドを使用すると、インスタント メッセージングのアーカイブは有効になりますが、Exchange へのアーカイブは無効になります (つまり、トランスクリプトは Skype for Business Server にアーカイブされます)。

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> EnableArchiving プロパティが None に設定されている場合、Skype for Business Server はインスタント メッセージングと Web 会議トランスクリプトをアーカイブしません。 この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。

Exchange アーカイブは、Skype for Business Server を使用して有効 (または無効) することもできます。 これを行うには、次の手順を実行します。

1. コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

2. [**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。

3. [**編集 アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。

4. アーカイブするアイテムを選択した後、[統合] チェック ボックスをオンExchange Server **Exchange** アーカイブを有効にします。 Exchange アーカイブを無効にするには、このチェック ボックスをオフにします。

> [!NOTE]
> [**アーカイブ設定**] が [**アーカイブを無効にする**] に設定されていると [**Exchange Server の統合**] チェック ボックスは利用できません。 まずアーカイブを有効にしてから、Exchange アーカイブを有効にする必要があります。

Skype for Business Server と Exchange Server が同じフォレスト内にある場合、個々のユーザー (または少なくとも Exchange Server の電子メール アカウントを持つユーザー) のアーカイブは、Exchange In-Place 保留ポリシーを使用して管理されます。 以前のバージョンの Exchange に保存されているユーザーがある場合、それらのユーザーのアーカイブは、Skype for Business Server アーカイブ ポリシーを使用して管理されます。 201 Exchange Server 6 または Exchange Server 2013 のアカウントを持つユーザーだけが、Skype for Business トランスクリプトを Exchange にアーカイブできる点に注意してください。

Skype for Business Server と Exchange Server が異なるフォレストにある場合、個々のユーザーのアーカイブは、個々のユーザー アカウントごとに ExchangeArchivingPolicy プロパティを構成することで管理されます。 詳細については、「手順 3」を参照してください。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする

アーカイブ (および Exchange アーカイブ) を有効にした後、適切なアーカイブ ポリシーを変更して、ユーザー セッションが実際にアーカイブされるのを確認する必要があります。 単にアーカイブを有効にしても (手順 1)、Skype for Business Server がインスタント メッセージングおよび Web 会議トランスクリプトのアーカイブを開始しない点に注意してください。 このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。 Skype for Business Server をインストールする場合は、次の 2 つのプロパティを含む単一のグローバル アーカイブ ポリシーもインストールします。

- **ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。

- **ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。

既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。 グローバル ポリシーを変更するには、Skype for Business Server 管理シェルと Set-CsArchivingPolicyできます。 次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

また、New-CsArchivingPolicy を使用して、サイト スコープまたはユーザーごとのスコープで新しいポリシーを作成することもできます。たとえば、次のコマンドを実行すると RedmondArchivingPolicy という名前の新しいユーザーごとのアーカイブ ポリシーが作成されます。

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

ユーザーごとのポリシーを作成した場合は、そのポリシーを適切なユーザーに割り当てる必要があります。次に例を示します。

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

アーカイブ ポリシーは、Skype for Business Server コントロール パネルを使用して管理することもできます。 コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。 既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。 新しいアーカイブ ポリシーを作成するには、[新規] **をクリック** し、[サイト ポリシー] または [ **ユーザー ポリシー]** **を選択します**。 新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>手順 3: ExchangeArchivingPolicy プロパティを構成する

Skype for Business Server と Exchange Serverが異なるフォレストにある場合は、アーカイブ構成設定で Exchange アーカイブを有効にするだけでは十分ではありません。インスタント メッセージングと Web 会議のトランスクリプトが Exchange にアーカイブされません。 代わりに、関連する各 Skype for Business Server ユーザー アカウントで ExchangeArchivingPolicy プロパティを構成する必要があります。 このプロパティは、次の 4 つの値のいずれかを設定できます。

1. **初期化されていない .** アーカイブがユーザーの Exchange メールボックス用に構成In-Place保持設定に基づいて行なうかどうかを示します。ユーザーIn-Placeメールボックスで保留が有効になっていない場合、ユーザーは自分のメッセージングと Web 会議のトランスクリプトを Skype for Business Server にアーカイブします。

2. **UseLyncArchivingPolicy**. ユーザーのインスタント メッセージングと Web 会議のトランスクリプトは、Exchange ではなく Skype for Business Server にアーカイブする必要があります。

3. **NoArchiving**. ユーザーのインスタント メッセージングと Web 会議のトランスクリプトをアーカイブしなけろと示します。 この設定は、ユーザーに割り当てられた Skype for Business Server アーカイブ ポリシーを上書きします。

4. **ArchivingToExchange**. ユーザーのメールボックスに割り当てられている (または割り当てられていない) In-Place 保留設定に関係なく、ユーザーのインスタント メッセージングおよび Web 会議トランスクリプトを Exchange にアーカイブする必要があります。

たとえば、インスタント メッセージングと Web 会議のトランスクリプトが常に Exchange にアーカイブされるユーザー アカウントを構成するには、Skype for Business Server 管理シェルから次のようなコマンドを使用できます。

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

ExchangeArchivingPolicy プロパティの値を構成するには、Skype for Business Server 管理シェル (および Windows PowerShell) を使用する必要があります。 このプロパティは、Skype for Business Server の管理者には公開されません。

特定のアーカイブ ポリシーを割り当てられているすべてのユーザーの一覧を表示するには、次のようなコマンドを使用します。このコマンドを実行すると、ExchangeArchivingPolicy プロパティが Uninitialized に設定されているすべてのユーザーの Active Directory 表示名が取得されます。

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同様に、次のコマンドを実行すると、ExchangeArchivingPolicy プロパティが UseLyncArchivingPolicy に設定されていないユーザーの表示名が取得されます。

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```