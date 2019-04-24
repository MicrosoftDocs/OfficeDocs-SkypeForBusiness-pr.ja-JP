---
title: Skype ビジネス サーバーで Exchange Server のアーカイブを使用するを構成します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: '概要: ビジネス サーバーの 2016 の Exchange Server や Exchange Server 2013 と Skype の IM のトラン スクリプトを構成します。'
ms.openlocfilehash: 5db51f1206fee5ef3f87f16e73836a32c460234b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216635"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Skype ビジネス サーバーで Exchange Server のアーカイブを使用するを構成します。

**の概要:** 2016 の Exchange Server や Exchange Server 2013 と Skype のビジネス サーバーの IM のトラン スクリプトを構成します。

ビジネス サーバー用の Skype は、インスタント メッセージング、Web 会議のトラン スクリプトが SQL Server データベースではなく、2016 の Exchange Server や Exchange Server 2013 のユーザーのメールボックスにアーカイブのオプションに管理者になります。 管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。 Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。 このフォルダーはエンドユーザーに表示するものではなく、フォルダーは Exchange の検索エンジンによってインデックスが作成されて、Exchange メールボックスの検索および Microsoft SharePoint Server 2013 を使用して探索することができます。 管理者がすべての電子通信のためのアーカイブを検索する 1 つのツールを使用できます Exchange インプレース保持機能 (電子メールやその他の Exchange の通信をアーカイブするための責任者) によって使用される同じフォルダーに情報が格納される、ため、ユーザーです。

> [!IMPORTANT]
> 会話のアーカイブを完全に無効にするには、会話の履歴も無効にする必要があります。 詳細については、次のトピックを参照してください:[ビジネス サーバーの Skype の内部と外部の通信のアーカイブを管理する](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)、[新しい CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)、および[セット CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。

Exchange Server に議事録を保存するために Skype ビジネス サーバーと Exchange Server 間でサーバーからサーバーへの認証を構成して開始する必要があります。 サーバーからサーバーへの認証が設定されて後を実行する Skype では、次のタスクのビジネス サーバー (のセットアップや構成によってする必要はありませんこれらすべてのタスクを完了するに注意してください)。

1. Skype をビジネス サーバー アーカイブ構成設定を変更することによって Exchange のアーカイブを有効にします。 この手順はすべての展開で必要です。

2. ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。 この手順はすべての展開で必要です。

3. 各ユーザーの ExchangeArchivingPolicy プロパティを構成します。 のみこの手順は、Skype のビジネス サーバーと Exchange Server が異なるフォレスト内にあるかどうかに必要です。

## <a name="step-1-enabling-exchange-archiving"></a>手順 1: Exchange のアーカイブの有効化

Skype ビジネス サーバーのアーカイブは、アーカイブの構成設定を使用して、主に管理されます。 ビジネス サーバーの Skype をインストールする場合は、これらの設定の 1 つのグローバル コレクションを自動的に与えられます。 (管理者オプションで作成できますアーカイブ設定のコレクションを新しいサイトのスコープで)。既定では、アーカイブが有効になっていない、グローバル設定でもこれらの設定で Exchange のアーカイブを有効にします。 Exchange のアーカイブを使用するには、管理者は、これらの構成設定で、EnableArchiving と EnableExchangeArchiving のプロパティの両方を構成する必要があります。 EnableArchiving プロパティは、3 つの値のいずれかに設定できます。

- **なし**。 アーカイブが無効になります。 これは既定の値です。 EnableArchiving は、[なし] に設定されてかどうかは、nothing になりますビジネス サーバーのデータベースをアーカイブするか、Exchange Server で、Skype をいずれかの方法でアーカイブします。

- **ImOnly**。 インスタント メッセージのトラン スクリプトのみがアーカイブされます。 Exchange のアーカイブを有効にすると、Exchange Server でこれらの証明書がアーカイブされます。 Exchange のアーカイブが無効になっている場合、これらの議事録にアーカイブされます Skype ビジネス サーバー。

- **ImAndWebConf**。 インスタント メッセージのトラン スクリプトと Web 会議の議事録の両方がアーカイブされます。 Exchange のアーカイブが有効になっている場合は、これらのトラン スクリプトは、Exchange Server でアーカイブされます。 Exchange のアーカイブが無効になっている場合、これらの議事録にアーカイブされます Skype ビジネス サーバー。

EnableExchangeArchiving プロパティは、ブール値: Exchange のアーカイブを無効にする場合は False ($False) に Exchange のアーカイブを有効にするまたは EnableExchangeArchiving を設定する場合は True ($True) に EnableExchangeArchiving を設定します。 たとえば、このコマンドは、インスタント メッセージングの議事録のアーカイブを有効にされ、Exchange のアーカイブすることもできます。

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Exchange のアーカイブを無効にするには、インスタント メッセージのアーカイブができますが、Exchange のアーカイブを無効にすると、次のようなコマンドを使用します (つまり、トラン スクリプトにアーカイブされます Skype ビジネス サーバー)。

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> EnableArchiving プロパティを [なし] に設定すると場合、Skype ビジネス サーバーはアーカイブ インスタント メッセージング、Web 会議の議事録に。 この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。

Exchange のアーカイブできますも有効 (または無効) ビジネス サーバーは、Skype を使用しています。 この操作を行うには、次の手順を実行します。

1. コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

2. [**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。

3. [**編集アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。

4. アーカイブする項目を選択すると、Exchange のアーカイブを有効にするのには、 **Exchange Server の統合**] チェック ボックスをオンにします。 Exchange のアーカイブを無効にするには、このチェック ボックスをオフにします。

> [!NOTE]
> [**アーカイブ設定**] が [**アーカイブを無効にする**] に設定されていると [**Exchange Server の統合**] チェック ボックスは利用できません。 最初のアーカイブを有効にして、Exchange のアーカイブを有効にする必要があります。

Skype ビジネス サーバーと Exchange Server の個々 のユーザーのアーカイブに、同じフォレスト内にある、(または少なくとも電子メールを持つユーザーのアカウントを Exchange Server 上) の場合は、Exchange インプレース保持ポリシーを使用して管理されます。 ある場合は、Business Server のアーカイブ ・ ポリシーの Skype を使用して、ホーム ユーザーのためのアーカイブし、Exchange の以前のバージョンにしているユーザーが管理されます。 2016 の Exchange Server や Exchange Server 2013 のアカウントを持つユーザーだけが、Skype をビジネス議事録の保存は、exchange のアーカイブを持つことができる注意してください。

Skype ビジネス サーバーと Exchange Server がある場合は、個々 のユーザー アカウントごとに ExchangeArchivingPolicy プロパティを設定することによって個々 のユーザーのアーカイブし、別のフォレストが管理されます。 詳細については、手順 3 を参照してください。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする

アーカイブを有効にして、アーカイブの交換) した後、ユーザー セッションが実際にアーカイブされることを確認するのには適切なアーカイブ ・ ポリシーを変更する必要があります。 (ステップ 1) のアーカイブを有効にするだけでも Skype のインスタント メッセージのアーカイブを開始するビジネス サーバーと Web 会議の議事録は発生しませんを注意してください。 このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。 ビジネス サーバーの Skype をインストールする場合は、2 つのプロパティが含まれています、1 つのグローバル アーカイブ ポリシーをインストールします。

- **ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。

- **ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。

既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。 グローバル ポリシーを変更するには、ビジネス サーバー管理シェルとコマンドレット セット CsArchivingPolicy、Skype を使用できます。 次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。

```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

また、New-CsArchivingPolicy を使用して、サイト スコープまたはユーザーごとのスコープで新しいポリシーを作成することもできます。たとえば、次のコマンドを実行すると RedmondArchivingPolicy という名前の新しいユーザーごとのアーカイブ ポリシーが作成されます。

```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

ユーザーごとのポリシーを作成した場合は、そのポリシーを適切なユーザーに割り当てる必要があります。次に例を示します。

```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

アーカイブ ポリシーは、ビジネス サーバーのコントロール パネルの Skype を使用して管理できます。 コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。 既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。 新しいアーカイブ ・ ポリシーを作成するには、[**新規**] をクリックし、**サイト ポリシー**または**ユーザー ポリシー**のいずれかを選択し、します。 新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>手順 3: ExchangeArchivingPolicy プロパティを構成する

Skype ビジネス サーバーと Exchange Server の別々 のフォレストに存在する場合、十分ではないアーカイブ、アーカイブの構成設定で Exchange を有効にするだけでインスタント メッセージングおよび Exchange アーカイブされている Web 会議の議事録には発生しません。 代わりに、各ビジネスのサーバーのユーザー アカウントに関連する Skype の ExchangeArchivingPolicy プロパティを構成することもする必要があります。 4 つの値のいずれかには、このプロパティを設定することができます。

1. **初期化されていません**。 埋め込み保持設定のユーザーの Exchange メールボックス用に構成されたアーカイブを基にすることを示します。インプレース保持、されていない場合は、ユーザーが自分のメッセージがあり、Web 会議の議事録が Skype ビジネス サーバーのアーカイブし、ユーザーのメールボックスで有効になっています。

2. **UseLyncArchivingPolicy**。 ユーザーのインスタント メッセージング、Web 会議の議事録をアーカイブする Exchange ではなく Skype ビジネス サーバーのことを示します。

3. **NoArchiving**。 ユーザーのインスタント メッセージング、Web 会議議事録を保存する必要がありますいないアーカイブすることすべてのことを示します。 アーカイブ ポリシーをユーザーに割り当てられているビジネス サーバーのこの設定が、Skype をオーバーライドすることに注意してください。

4. **ArchivingToExchange**。 示しますユーザーのインスタント メッセージングと Web 会議埋め込み保持設定にかかわらず、Exchange にトラン スクリプトをアーカイブすることがある (またはない) は、ユーザーのメールボックスに割り当てられています。

たとえば、インスタント メッセージング、Web 会議の議事録を常に Exchange をアーカイブするためにユーザー アカウントを構成するのには、ビジネス サーバー管理シェルの Skype から次のようなコマンドを使用できます。

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

ビジネス サーバー管理シェル (および Windows PowerShell) ExchangeArchivingPolicy プロパティの値を構成するために Skype を使用する必要があることに注意してください。 このプロパティは、ビジネスのサーバーに、Skype での管理者に公開されません。

特定のアーカイブ ポリシーを割り当てられているすべてのユーザーの一覧を表示するには、次のようなコマンドを使用します。このコマンドを実行すると、ExchangeArchivingPolicy プロパティが Uninitialized に設定されているすべてのユーザーの Active Directory 表示名が取得されます。

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同様に、次のコマンドを実行すると、ExchangeArchivingPolicy プロパティが UseLyncArchivingPolicy に設定されていないユーザーの表示名が取得されます。

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


