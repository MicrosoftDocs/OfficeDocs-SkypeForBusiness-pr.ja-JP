---
title: Skype for Business Server がアーカイブを使用Exchange Server構成する
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
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server の IM トランスクリプトを構成します。'
ms.openlocfilehash: f051e5f3798b76b5e3943893d2a18e113ae8ab16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833897"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Skype for Business Server がアーカイブを使用Exchange Server構成する

**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server の IM トランスクリプトを構成します。

Skype for Business Server を使用すると、管理者はインスタント メッセージングと Web 会議のトランスクリプトを SQL Server データベースではなくユーザーの Exchange Server 2016 または Exchange Server 2013 メールボックスにアーカイブできます。 管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。 Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。 このフォルダーはエンド ユーザーには表示されませんが、Exchange 検索エンジンによってインデックスが作成され、Exchange メールボックス検索や Microsoft SharePoint Server 2013 を使用して検出できます。 情報は Exchange In-Place 保留機能 (電子メールおよび他の Exchange 通信のアーカイブを担当) で使用されるフォルダーと同じフォルダーに格納されるので、管理者は単一のツールを使用して、ユーザーにアーカイブされた電子通信を検索できます。

> [!IMPORTANT]
> 会話のアーカイブを完全に無効にするには、会話履歴も無効にする必要があります。 詳細については、次のトピックを参照してください: [Skype for Business](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)Server、New-CsClientPolicy、および [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)での内部通信と外部通信のアーカイブの [管理](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。

トランスクリプトをアーカイブして Exchange Serverするには、まず、Skype for Business Server と Exchange Server の間でサーバー間認証を構成する必要があります。 サーバー間認証が実施された後、Skype for Business Server で次のタスクを実行できます (セットアップと構成によっては、これらのタスクの一部を完了する必要が生じ得ない場合があります)。

1. Skype for Business Server のアーカイブ構成設定を変更して、Exchange アーカイブを有効にします。 この手順はすべての展開で必要です。

2. ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。 この手順はすべての展開で必要です。

3. 各ユーザーの ExchangeArchivingPolicy プロパティを構成します。 この手順が必要になるのは、Skype for Business Server と Exchange Serverが異なるフォレストにある場合のみです。

## <a name="step-1-enabling-exchange-archiving"></a>手順 1: Exchange アーカイブを有効にする

Skype for Business Server のアーカイブは、主にアーカイブ構成設定を使用して管理されます。 Skype for Business Server をインストールすると、これらの設定の 1 つのグローバル コレクションが自動的に提供されます。 (管理者は、必要に応じて、サイト スコープでアーカイブ設定の新しいコレクションを作成できます)。既定では、グローバル設定ではアーカイブは有効ではなく、これらの設定では Exchange アーカイブも有効になっていません。 Exchange アーカイブを使用するには、管理者は、これらの構成設定で EnableArchiving プロパティと EnableExchangeArchiving プロパティの両方を構成する必要があります。 EnableArchiving プロパティは、次の 3 つの値のいずれかを設定できます。

- **なし**。 アーカイブは無効です。 これが既定値です。 EnableArchiving が None に設定されている場合、Skype for Business Server アーカイブ データベースまたはアーカイブ データベースに何もアーカイブExchange Server。

- **ImOnly**. インスタント メッセージのトランスクリプトだけがアーカイブされます。 Exchange のアーカイブが有効になっている場合、これらのトランスクリプトは次のExchange Server。 Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Skype for Business Server にアーカイブされます。

- **ImAndWebConf**. インスタント メッセージのトランスクリプトと Web 会議のトランスクリプトの両方がアーカイブされます。 Exchange アーカイブが有効になっている場合、これらのトランスクリプトは、次のExchange Server。 Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Skype for Business Server にアーカイブされます。

EnableExchangeArchiving プロパティはブール値です。EnableExchangeArchiving を True ($True) に設定して Exchange アーカイブを有効にするか、EnableExchangeArchiving を False ($False) に設定して Exchange アーカイブを無効にします。 たとえば、次のコマンドを実行すると、インスタント メッセージングのトランスクリプトのアーカイブが有効にされ、Exchange のアーカイブも有効にされます。

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Exchange アーカイブを無効にするには、次のようなコマンドを使用します。このコマンドを使用すると、インスタント メッセージングのアーカイブは有効になりますが、Exchange へのアーカイブは無効になります (つまり、トランスクリプトは Skype for Business Server にアーカイブされます)。

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> EnableArchiving プロパティが None に設定されている場合、Skype for Business Server はインスタント メッセージングと Web 会議のトランスクリプトをアーカイブしません。 この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。

Exchange アーカイブは、Skype for Business Server を使用して有効 (または無効) にすることもできます。 これを行うには、次の手順を実行します。

1. コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

2. [**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。

3. [**編集 アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。

4. アーカイブするアイテムを選択した後、exchange アーカイブを有効にするにはExchange Server統合チェック ボックスをオンにします。 Exchange アーカイブを無効にするには、このチェック ボックスをオフにします。

> [!NOTE]
> [**アーカイブ設定**] が [**アーカイブを無効にする**] に設定されていると [**Exchange Server の統合**] チェック ボックスは利用できません。 最初にアーカイブを有効にしてから、Exchange アーカイブを有効にする必要があります。

Skype for Business Server と Exchange Server が同じフォレストにある場合、個々のユーザー (または少なくとも Exchange Server の電子メール アカウントを持つユーザー) のアーカイブは、Exchange In-Place 保留ポリシーを使用して管理されます。 以前のバージョンの Exchange にホームを持つユーザーがある場合、それらのユーザーのアーカイブは Skype for Business Server アーカイブ ポリシーを使用して管理されます。 Exchange Server 2016 または Exchange Server 2013 のアカウントを持つユーザーだけが、Skype for Business のトランスクリプトを Exchange にアーカイブできます。

Skype for Business Server と Exchange Server が異なるフォレストにある場合、個々のユーザーのアーカイブは、個々のユーザー アカウントごとに ExchangeArchivingPolicy プロパティを構成することで管理されます。 詳細については、手順 3 を参照してください。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする

アーカイブ (および Exchange アーカイブ) を有効にした後、適切なアーカイブ ポリシーを変更して、ユーザー セッションが実際にアーカイブされる必要があります。 アーカイブ (手順 1) を有効にするだけでは、Skype for Business Server がインスタント メッセージングと Web 会議のトランスクリプトのアーカイブを開始しない点に注意してください。 このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。 Skype for Business Server をインストールすると、次の 2 つのプロパティを含む単一のグローバル アーカイブ ポリシーもインストールされます。

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

アーカイブ ポリシーは、Skype for Business Server コントロール パネルを使用して管理することもできます。 コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。 既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。 新しいアーカイブ ポリシーを作成するには、[新規] **をクリックし** 、[サイト ポリシー] または [ユーザー **ポリシー]** を **選択します**。 新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>手順 3: ExchangeArchivingPolicy プロパティを構成する

Skype for Business Server と Exchange Server が別のフォレストにある場合は、単にアーカイブ構成設定で Exchange アーカイブを有効にするだけでは十分ではありません。この場合、インスタント メッセージングと Web 会議のトランスクリプトは Exchange にアーカイブされません。 代わりに、関連する各 Skype for Business Server ユーザー アカウントで ExchangeArchivingPolicy プロパティを構成する必要があります。 このプロパティには、次の 4 つの値のいずれかを設定できます。

1. **Uninitialized**. アーカイブが、ユーザーの Exchange メールボックスに対してIn-Place設定に基づくかどうかを示します。ユーザーIn-Placeホールドが有効になっていない場合、ユーザーは自分のメッセージングおよび Web 会議のトランスクリプトを Skype for Business Server にアーカイブします。

2. **UseLyncArchivingPolicy**. ユーザーのインスタント メッセージングおよび Web 会議のトランスクリプトは、Exchange ではなく Skype for Business Server にアーカイブする必要があります。

3. **NoArchiving**. ユーザーのインスタント メッセージングおよび Web 会議のトランスクリプトを一部アーカイブしなけずに示します。 この設定は、ユーザーに割り当てられた Skype for Business Server のアーカイブ ポリシーより優先されます。

4. **ArchivingToExchange**. ユーザーのメールボックスに割り当てられている (または割り当てられていない) In-Place 保留設定に関係なく、ユーザーのインスタント メッセージングおよび Web 会議のトランスクリプトを Exchange にアーカイブする必要があります。

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


