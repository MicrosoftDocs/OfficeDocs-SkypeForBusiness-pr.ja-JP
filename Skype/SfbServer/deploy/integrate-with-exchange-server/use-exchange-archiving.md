---
title: アーカイブSkype for Business Server使用するExchange Server構成する
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: '概要: 2016 年または 2016 年Exchange Server 2013 年および 2013 年Exchange Server IM トランスクリプトを構成Skype for Business Server。'
ms.openlocfilehash: f264b347660df032b67f06ddf605e99ba97a32b2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603064"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>アーカイブSkype for Business Server使用するExchange Server構成する

**概要:** 2016 年または 2016 年Exchange Server 2013 年およびExchange Serverの IM トランスクリプトをSkype for Business Server。

Skype for Business Server管理者は、インスタント メッセージングと Web 会議のトランスクリプトを、SQL Server データベースではなく、ユーザーの Exchange Server 2016 または Exchange Server 2013 メールボックスにアーカイブするオプションを提供します。 管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。 Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。 このフォルダーはエンド ユーザーには表示されませんが、フォルダーは Exchange 検索エンジンによってインデックス付けされ、Exchange メールボックス検索および/または 2013 年Microsoft SharePoint Server使用して検出できます。 Exchange In-Place 保留機能 (電子メールなどの Exchange 通信のアーカイブを担当する) で使用される同じフォルダーに情報が格納されるので、管理者は 1 つのツールを使用して、ユーザーにアーカイブされた電子通信を検索できます。

> [!IMPORTANT]
> 会話のアーカイブを完全に無効にするには、会話履歴も無効にする必要があります。 詳細については[、「Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications) [、New-CsClientPolicy、](/powershell/module/skype/new-csclientpolicy?view=skype-ps)[および Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps)での内部および外部通信のアーカイブの管理」を参照してください。

トランスクリプトをサーバーにアーカイブするにはExchange Serverサーバー間認証をサーバー間で構成し、Skype for Business ServerをExchange Server。 サーバー間認証が実行された後、Skype for Business Server で次のタスクを実行できます (セットアップと構成によっては、これらのタスクの一部を完了する必要が生じない場合があります)。

1. アーカイブExchange構成設定を変更して、Skype for Business Serverアーカイブを有効にします。 この手順はすべての展開で必要です。

2. ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。この手順はすべての展開で必要です。

3. 各ユーザーの ExchangeArchivingPolicy プロパティを構成します。 この手順は、別のフォレストにSkype for Business ServerとExchange Server場合にのみ必要です。

## <a name="step-1-enabling-exchange-archiving"></a>手順 1: アーカイブのExchangeする

アーカイブは、Skype for Business Server構成設定を使用して主に管理されます。 これらの設定をインストールSkype for Business Server、これらの設定の単一のグローバル コレクションが自動的に与えられる。 (管理者は、必要に応じて、サイト スコープでアーカイブ設定の新しいコレクションを作成できます)。既定では、グローバル設定ではアーカイブは有効にされません。また、これらのExchangeでアーカイブが有効になっている場合もありません。 このアーカイブを使用Exchange管理者は、これらの構成設定で EnableArchiving プロパティと EnableExchangeArchiving プロパティの両方を構成する必要があります。 EnableArchiving プロパティは、次の 3 つの値のいずれかを設定できます。

- **なし 。** アーカイブは無効です。 これが既定値です。 EnableArchiving が None に設定されている場合、アーカイブ データベースまたはアーカイブ データベースにアーカイブSkype for Business Server何もアーカイブExchange Server。

- **ImOnly**. インスタント メッセージトランスクリプトだけがアーカイブされます。 アーカイブExchange有効になっている場合、これらのトランスクリプトは、アーカイブにアーカイブExchange Server。 アーカイブExchange無効になっている場合、これらのトランスクリプトはアーカイブにアーカイブSkype for Business Server。

- **ImAndWebConf**. インスタント メッセージトランスクリプトと Web 会議トランスクリプトの両方がアーカイブされます。 アーカイブExchange有効になっている場合、これらのトランスクリプトはアーカイブにアーカイブExchange Server。 アーカイブExchange無効になっている場合、これらのトランスクリプトはアーカイブにアーカイブSkype for Business Server。

EnableExchangeArchiving プロパティはブール値です。EnableExchangeArchiving を True ($True) に設定して Exchange アーカイブを有効にするか、EnableExchangeArchiving を False ($False) に設定して Exchange アーカイブを無効にします。 たとえば、このコマンドを使用すると、インスタント メッセージング トランスクリプトのアーカイブが有効にされ、次のExchangeできます。

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Exchange アーカイブを無効にするには、次のようなコマンドを使用して、インスタント メッセージングのアーカイブを有効にしますが、Exchange へのアーカイブを無効にします (つまり、トランスクリプトは Skype for Business Server にアーカイブされます)。

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> EnableArchiving プロパティが [なし] に設定されている場合、Skype for Business Serverはインスタント メッセージングと Web 会議トランスクリプトをアーカイブしない。 この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。

Exchangeを使用して、アーカイブを有効 (または無効) にSkype for Business Server。 これを行うには、次の手順を実行します。

1. コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

2. [**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。

3. [**編集 アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。

4. アーカイブするアイテムを選択した後、[統合] Exchange Serverを選択して、アーカイブExchangeします。 アーカイブを無効Exchange、このチェック ボックスをオフにします。

> [!NOTE]
> [**アーカイブ設定**] が [**アーカイブを無効にする**] に設定されていると [**Exchange Server の統合**] チェック ボックスは利用できません。 最初にアーカイブを有効にしてから、アーカイブを有効Exchange必要があります。

Skype for Business Server と Exchange Server が同じフォレスト内にある場合は、個々のユーザー (または少なくとも Exchange Server で電子メール アカウントを持つユーザー) のアーカイブは、Exchange In-Place 保留ポリシーを使用して管理されます。 以前のバージョンの Exchangeユーザーがある場合、それらのユーザーのアーカイブは、Skype for Business Server使用して管理されます。 2016 または Exchange Server Exchange Server 2013 のアカウントを持つユーザーだけが、Skype for Business トランスクリプトを Exchange にアーカイブできます。

別Skype for Business ServerとExchange Serverが異なるフォレストにある場合、個々のユーザーのアーカイブは、個々のユーザー アカウントごとに ExchangeArchivingPolicy プロパティを構成することで管理されます。 詳細については、「手順 3」を参照してください。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする

アーカイブを有効にした後 (およびアーカイブExchange)、適切なアーカイブ ポリシーを変更して、ユーザー セッションが実際にアーカイブされるのを確認する必要があります。 単にアーカイブを有効にしても (手順 1) では、インスタント メッセージングSkype for Business Server Web 会議のトランスクリプトのアーカイブを開始する必要が生じ得ない点に注意してください。 このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。 サーバーをインストールSkype for Business Server、2 つのプロパティを含む単一のグローバル アーカイブ ポリシーもインストールします。

- **ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。

- **ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。

既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。 グローバル ポリシーを変更するには、管理シェルと Skype for Business ServerコマンドレットをSet-CsArchivingPolicyできます。 次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。

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

アーカイブ ポリシーは、[コントロール パネル] コントロール パネルを使用Skype for Business Server管理することもできます。 コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。 既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。 新しいアーカイブ ポリシーを作成するには、[新規] **をクリック** し、[サイト ポリシー] または [ **ユーザー ポリシー]** **を選択します**。 新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>手順 3: ExchangeArchivingPolicy プロパティを構成する

複数Skype for Business ServerおよびExchange Serverフォレストにある場合は、アーカイブ構成設定でアーカイブを有効Exchangeするだけでは十分ではありません。インスタント メッセージングや Web 会議のトランスクリプトが、インスタント メッセージングや Web 会議のトランスクリプトExchange。 代わりに、関連する各ユーザー アカウントで ExchangeArchivingPolicy プロパティSkype for Business Server必要があります。 このプロパティは、次の 4 つの値のいずれかを設定できます。

1. **初期化されていない .** アーカイブがユーザーのメールボックス用に構成In-Place保持設定に基づくExchangeします。ユーザーIn-Placeメールボックスで保留が有効になっていない場合、ユーザーはメッセージングと Web 会議のトランスクリプトを Skype for Business Server にアーカイブします。

2. **UseLyncArchivingPolicy**. ユーザーのインスタント メッセージングと Web 会議のトランスクリプトを、Skype for Business Serverではなく、Exchange。

3. **NoArchiving**. ユーザーのインスタント メッセージングと Web 会議のトランスクリプトをアーカイブしなけろと示します。 この設定は、ユーザーに割り当Skype for Business Serverアーカイブ ポリシーを上書きします。

4. **ArchivingToExchange**. ユーザーのメールボックスに割り当てられている (または割り当てられていない) In-Place 保留設定に関係なく、ユーザーのインスタント メッセージングおよび Web 会議トランスクリプトを Exchange にアーカイブする必要があります。

たとえば、インスタント メッセージングと Web 会議のトランスクリプトが常に Exchange にアーカイブされるユーザー アカウントを構成するには、Skype for Business Server 管理シェルから次のようなコマンドを使用できます。

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

ExchangeArchivingPolicy プロパティの値を構成するには、Skype for Business Server管理シェル (および Windows PowerShell) を使用する必要があります。 このプロパティは、管理者が管理者に公開Skype for Business Server。

特定のアーカイブ ポリシーを割り当てられているすべてのユーザーの一覧を表示するには、次のようなコマンドを使用します。このコマンドを実行すると、ExchangeArchivingPolicy プロパティが Uninitialized に設定されているすべてのユーザーの Active Directory 表示名が取得されます。

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同様に、次のコマンドを実行すると、ExchangeArchivingPolicy プロパティが UseLyncArchivingPolicy に設定されていないユーザーの表示名が取得されます。

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```