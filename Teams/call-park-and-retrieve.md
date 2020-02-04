---
title: Microsoft Teams でのコール パークおよび保留解除
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- ms.teamsadmincenter.callparkpolicies.overview
ms.custom:
- Phone System
description: '[コールパーク] を使って、クラウドの Teams サービスで通話を保留にします。'
ms.openlocfilehash: 4bd77fcd90cb17f0ca5b09f784d6532d552df473
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695622"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams でのコール パークおよび保留解除

[コールパーク] と [取得] は、ユーザーがクラウドの Teams サービスで通話を保留できるようにする機能です。 通話が保留中の場合、サービスは通話の取得用に一意のコードを生成します。 通話または他のユーザーが、そのコードとサポートされているアプリまたはデバイスを使って通話を取得できます。 

コールパークを使用する一般的なシナリオには、次のようなものがあります。 

- 受付係は、工場で仕事をしている人のために電話をかけます。 次に、受付によって、通話とコード番号がパブリックアドレスシステム経由でアナウンスされます。 次に、通話を発信しているユーザーは、工場のフロアで Teams 電話を選択して、通話を取得するためのコードを入力することができます。
- デバイスのバッテリーの電力が不足しているため、ユーザーがモバイルデバイスで通話をパークしています。 次に、ユーザーはコードを入力して、Teams 卓上電話から通話を取得できます。
- サポート担当者は、顧客からの通話をパークし、専門家が通話を取得して顧客を支援するためにチームチャネルでお知らせを送信します。 エキスパートが Teams クライアントにコードを入力して通話を取得する

> [!IMPORTANT]
> この機能は、Teams のみの展開モードでのみ利用できます。 Teams の展開モードの詳細については、「 [Microsoft Teams と Skype For business の共存と相互運用性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)について」を参照してください。

## <a name="license-required"></a>ライセンスが必要

通話をパークして取得するには、ユーザーはエンタープライズボイスユーザーである必要があります。管理者は、ユーザーにコールパークポリシーを与える必要があります。 ライセンスモデルの詳細については、「 [Microsoft Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。

## <a name="call-park-and-retrieve-feature-availability"></a>通話パークと機能の可用性の取得

コールパークと取得は、現在次のクライアントとデバイスでサポートされています。 (チーム専用モードでサポートされています。 PSTN 接続の有無はサポートされています)。

| 機能 | Teams のデスクトップ | Teams Mac アプリ | Teams Web App (Edge) |Teams mobile iOS/Android アプリ | Teams の IP 電話 | Skype for Business の IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 通話をパークする | はい | はい | はい | はい | もうすぐです| いいえ |
| 保留中の通話を取得する | はい | はい | はい | はい | もうすぐです| いいえ |
| 着信コールバックの取り消し | はい | はい | はい | はい | もうすぐです| いいえ |

## <a name="configuring-call-park-and-retrieve"></a>コールパークと取得の構成

コールパークを構成して取得するには、管理者である必要があります。この機能は、既定では無効になっています。 ユーザーに対して有効にし、[コールパーク] ポリシーを使用してユーザーグループを作成することができます。 同じポリシーを一連のユーザーに適用すると、その間で通話をパークして取得することができます。 ユーザー用のコールパークを構成し、コールパークのユーザーグループを作成するには、以下の「[コールパークポリシーの割り当て](#assign-a-call-park-policy)」の手順に従います。

コールパークを使用して機能を取得する方法については、「 [Teams で通話をパーク](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)する」を参照してください。

### <a name="enable-a-call-park-policy"></a>コールパークポリシーを有効にする

次の手順に従って、コールパークポリシーを有効にします。

1. **Microsoft Teams 管理センター** > の**音声** > **通話パークポリシー**に移動します。
2. [**新しいポリシー**] を選びます。
3. ポリシーに名前を付け、[ **Call パークを有効**にする] に切り替え**ます。**
4. [**保存**] を選びます。

### <a name="assign-a-call-park-policy"></a>コールパークポリシーを割り当てる

次の手順に従って、1人以上のユーザーにコールパークポリシーを割り当てます。

1. **Microsoft Teams 管理センター** > の**音声** > **通話パークポリシー**に移動します。
2. ポリシー名の左側をクリックして、ポリシーを選択します。
3. [**ユーザーの管理**] を選びます。
4. [**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、[**保存**] を選択します。
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>PowerShell を使用したコールパークと取得の構成

[新しい-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用して、コールパークポリシーを作成します。

コールパークポリシーを付与するには、 [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用します。

既定の設定を変更するには、次のように、 [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)を使用します。

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>トラブルシューティング

ユーザーが [パーク] または [取得] ボタンを表示できない場合: 

- ユーザーがコールパークポリシーを有効にしていることを確認します。 

ユーザーが通話を取得しようとして失敗した場合は、次のことを確認してください。

- ユーザーがチームクライアントまたはチーム対応デバイス/スマートフォンを使用していることを確認する
- グループ化–ユーザーは [コールパーク] グループのメンバーになっています。このグループは、同じ Teams Call パークポリシーが割り当てられていることに基づいています。 
- アイランドモード– Teams アイランドモードでは、コールパークと取得は利用できません。
- 通話は既に取得または終了されています。

## <a name="more-information"></a>詳細情報

[Teams で通話をパーク](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)します。
