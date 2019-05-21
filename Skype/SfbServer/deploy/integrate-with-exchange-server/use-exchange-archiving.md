---
title: Exchange Server のアーカイブを使用するように Skype for Business Server を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server の IM トランスクリプトを構成します。'
ms.openlocfilehash: b24353a9742a48b35e21ac00df40a04fa60e444b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278071"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Exchange Server のアーカイブを使用するように Skype for Business Server を構成する

**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server の IM トランスクリプトを構成します。

Skype for Business Server を使用すると、管理者は、インスタントメッセージと Web 会議のトランスクリプトを、SQL Server データベースではなく、ユーザーの Exchange Server 2016 または Exchange Server 2013 メールボックスにアーカイブするオプションが提供されます。 管理者がこのオプションを有効にすると、トランスクリプトはユーザーのメールボックスの Purges フォルダーに書き込まれます。 Purges フォルダーは、Recoverable Items フォルダーにある隠しフォルダーです。 このフォルダーはエンドユーザーには表示されませんが、Exchange のメールボックス検索、または Microsoft SharePoint Server 2013 を使って、フォルダーに Exchange 検索エンジンでインデックスが付けられています。 情報は、Exchange のインプレースホールド機能で使用されているものと同じフォルダー (メールのアーカイブおよびその他の Exchange 通信を担当します) に保存されているため、管理者は、1つのツールを使用してアーカイブされているすべての電子通信を検索することができます。ユーザーズ.

> [!IMPORTANT]
> 会話のアーカイブを完全に無効にするには、会話の履歴も無効にする必要があります。 詳細については、次のトピックを参照してください。 Skype for Business Server、[新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)、および[Set csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)[での内部および外部通信のアーカイブの管理](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)

Exchange Server にトランスクリプトをアーカイブするには、まず Skype for Business Server と Exchange Server の間のサーバー間認証を構成する必要があります。 サーバー間認証が行われた後、Skype for Business Server で次のタスクを実行できます (ただし、セットアップと構成によっては、これらのすべてのタスクを完了する必要がない場合があることに注意してください)。

1. Exchange のアーカイブを有効にするには、Skype for Business Server のアーカイブ構成設定を変更します。 この手順はすべての展開で必要です。

2. ユーザーの内部通信と外部通信のどちらかまたは両方のアーカイブを有効にします。 この手順はすべての展開で必要です。

3. 各ユーザーの ExchangeArchivingPolicy プロパティを構成します。 この手順は、Skype for Business Server と Exchange Server が異なるフォレストにある場合にのみ必要です。

## <a name="step-1-enabling-exchange-archiving"></a>手順 1: Exchange のアーカイブを有効にする

Skype for Business Server のアーカイブは、主にアーカイブ構成設定を使用して管理されます。 Skype for Business Server をインストールすると、これらの設定のグローバルコレクションが自動的に1つ提供されます。 (管理者は、必要に応じて、サイトのスコープでアーカイブ設定の新しいコレクションを作成することができます)。既定では、グローバル設定ではアーカイブが有効になっていません。また、これらの設定では Exchange アーカイブが有効になっていません。 Exchange のアーカイブを使用するには、管理者は、これらの構成設定で EnableArchiving と Enableexchangeアーカイブの両方のプロパティを設定する必要があります。 EnableArchiving プロパティは、次の3つの値のいずれかに設定できます。

- **なし**。 アーカイブが無効になっています。 これは既定の値です。 EnableArchiving が None に設定されている場合、Skype for Business Server アーカイブデータベースまたは Exchange Server のいずれにもアーカイブされません。

- **Imonly**。 インスタントメッセージのトランスクリプトのみがアーカイブされます。 Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange Server にアーカイブされます。 Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Skype for Business Server にアーカイブされます。

- **Imandwebconf**。 インスタントメッセージのトランスクリプトと Web 会議のトランスクリプトは両方ともアーカイブされます。 Exchange アーカイブが有効になっている場合、これらのトランスクリプトは Exchange Server にアーカイブされます。 Exchange アーカイブが無効になっている場合、これらのトランスクリプトは Skype for Business Server にアーカイブされます。

EnableExchangeArchiving プロパティは、"EnableExchangeArchiving を True ($True)" に設定して Exchange アーカイブを有効にするか、EnableExchangeArchiving を False ($False) に設定して Exchange のアーカイブを無効にすることができます。 たとえば、次のコマンドを実行すると、インスタントメッセージのトランスクリプトがアーカイブされ、Exchange アーカイブも有効になります。

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Exchange のアーカイブを無効にするには、次のようなコマンドを使用します。これにより、インスタントメッセージアーカイブは可能になりますが、Exchange へのアーカイブは無効になります (つまり、トランスクリプトは Skype for Business Server にアーカイブされます)。

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> EnableArchiving プロパティが None に設定されている場合、Skype for Business Server では、インスタントメッセージングと Web 会議のトランスクリプトはまったくアーカイブされません。 この場合、サーバーは単に EnableExchangeArchiving に構成されている値を無視します。

Exchange アーカイブは、Skype for Business Server を使用して有効 (または無効) にすることもできます。 この操作を行うには、次の手順を実行します。

1. コントロール パネルで、[**監視およびアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

2. [**アーカイブ構成**] タブで、変更するアーカイブ設定のコレクション ([**グローバル**] コレクションなど) をダブルクリックします。

3. [**編集アーカイブ設定**] ウィンドウで、[**アーカイブ設定**] ドロップダウン リストをクリックし、[**IM セッションをアーカイブする**] (インスタント メッセージング セッションのみをアーカイブする場合) または [**IM および Web 会議セッションをアーカイブする**] (インスタント メッセージング セッションと Web 会議セッションの両方をアーカイブする場合) のどちらかを選択します。

4. アーカイブする項目を選んだら、[ **Exchange Server 統合**] チェックボックスをオンにして、exchange アーカイブを有効にします。 Exchange のアーカイブを無効にするには、このチェックボックスをオフにします。

> [!NOTE]
> [**アーカイブ設定**] が [**アーカイブを無効にする**] に設定されていると [**Exchange Server の統合**] チェック ボックスは利用できません。 最初にアーカイブを有効にしてから、Exchange アーカイブを有効にする必要があります。

Skype for Business Server と Exchange Server が同じフォレストに配置されている場合、個々のユーザー (または少なくとも Exchange Server のメールアカウントを持つユーザー) のアーカイブは、Exchange のインプレースホールドポリシーを使って管理されます。 以前のバージョンの Exchange を使用しているユーザーがいる場合、それらのユーザーのアーカイブは、Skype for Business Server のアーカイブポリシーを使って管理されます。 Exchange Server 2016 または Exchange Server 2013 上のアカウントを持つユーザーのみが、Skype for Business のトランスクリプトを Exchange にアーカイブすることができます。

Skype for Business Server と Exchange Server が異なるフォレストに配置されている場合、個々のユーザー用のアーカイブは、個々のユーザーアカウントの ExchangeArchivingPolicy プロパティを構成することによって管理されます。 詳細については、手順3を参照してください。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>手順 2: 内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする

アーカイブ (および Exchange のアーカイブ) を有効にした後、適切なアーカイブポリシーを変更して、ユーザーセッションが実際にアーカイブされることを確認する必要があります。 アーカイブを有効にする (手順 1) だけでは、Skype for Business Server でインスタントメッセージングと Web 会議のトランスクリプトのアーカイブが開始されることはありません。 このため、アーカイブ ポリシーを使用して内部通信と外部通信のどちらかまたは両方のアーカイブを有効にする必要があります。 Skype for Business Server をインストールする場合は、次の2つのプロパティを含む単一のグローバルアーカイブポリシーもインストールします。

- **ArchiveInternal**: True ($True) に設定すると、組織の Active Directory アカウントを持つユーザーのみが参加している内部通信セッションがアーカイブされます。

- **ArchiveExternal**: True ($True) に設定すると、内部通信セッション (組織の Active Directory アカウントを持たないユーザーが少なくとも 1 人参加しているセッション) がアーカイブされます。

既定では、これらのプロパティの値はどちらも False に設定されており、内部通信セッションも外部通信セッションもアーカイブされません。 グローバルポリシーを変更するには、Skype for Business Server 管理シェルと CsArchivingPolicy コマンドレットを使用します。 次のコマンドを実行すると、内部通信セッションと外部通信セッションの両方のアーカイブが有効になります。

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

また、アーカイブポリシーは、Skype for Business Server コントロールパネルを使用して管理することもできます。 コントロール パネル内で、[**監視およびアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。 既存のポリシーを変更するには、ポリシー ([グローバル] など) をダブルクリックし、[**アーカイブ ポリシーの編集**] ウィンドウで、[**内部通信をアーカイブする**] および [**外部通信をアーカイブする**] チェック ボックスを必要に応じてオンまたはオフにします。 新しいアーカイブポリシーを作成するには、[**新規**] をクリックし、[**サイトポリシー** ] または [**ユーザーポリシー**] を選びます。 新しいユーザー ポリシーを作成した場合は、適切なユーザー アカウントに ([**ユーザー**] タブから) アクセスし、ユーザーに新しいポリシーを割り当てる必要があります。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>手順 3: ExchangeArchivingPolicy プロパティを構成する

Skype for Business Server と Exchange Server が異なるフォレストに配置されている場合は、アーカイブ構成設定で Exchange アーカイブを有効にするだけでは十分ではありません。これにより、インスタントメッセージと Web 会議のトランスクリプトは Exchange にアーカイブされません。 代わりに、関連する各 Skype for Business Server ユーザーアカウントの ExchangeArchivingPolicy プロパティも構成する必要があります。 このプロパティは、次の4つの値のいずれかに設定できます。

1. **未初期化**。 アーカイブが、ユーザーの Exchange メールボックスに対して構成されているインプレースホールド設定に基づいていることを示します。ユーザーのメールボックスでインプレース保持が有効になっていない場合、ユーザーには、そのユーザーのメッセージングと Web 会議の議事録が Skype for Business Server にアーカイブされます。

2. **UseLyncArchivingPolicy**。 ユーザーのインスタントメッセージングおよび Web 会議のトランスクリプトを、Exchange ではなく Skype for Business Server にアーカイブする必要があることを示します。

3. **Noarchiving**。 ユーザーのインスタントメッセージングと Web 会議のトランスクリプトがまったくアーカイブされないことを示します。 この設定は、ユーザーに割り当てられている Skype for Business Server のアーカイブポリシーよりも優先されることに注意してください。

4. **ArchivingToExchange**。 ユーザーのインスタントメッセージングおよび Web 会議のトランスクリプトが、ユーザーのメールボックスに割り当てられている (または使用されていない) インプレースホールドの設定に関係なく、Exchange にアーカイブされることを示します。

たとえば、インスタントメッセージングと Web 会議のトランスクリプトが常に Exchange にアーカイブされるようにユーザーアカウントを構成するには、次のようなコマンドを Skype for Business Server 管理シェルから使うことができます。

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

ユーザーのグループ (たとえば、指定したレジストラー プールに所属するすべてのユーザー) に同じアーカイブ ポリシーを設定する場合は、次のようなコマンドを使用します。

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

ExchangeArchivingPolicy プロパティの値を構成するためには、Skype for Business Server 管理シェル (および Windows PowerShell) を使用する必要があることに注意してください。 このプロパティは、Skype for Business Server の管理者には公開されません。

特定のアーカイブ ポリシーを割り当てられているすべてのユーザーの一覧を表示するには、次のようなコマンドを使用します。このコマンドを実行すると、ExchangeArchivingPolicy プロパティが Uninitialized に設定されているすべてのユーザーの Active Directory 表示名が取得されます。

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同様に、次のコマンドを実行すると、ExchangeArchivingPolicy プロパティが UseLyncArchivingPolicy に設定されていないユーザーの表示名が取得されます。

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


