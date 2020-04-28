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
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 電話会議を使って、クラウドの Teams サービスで通話を保留にする方法について説明します。
ms.openlocfilehash: 2420652fc908a943e798ac1acade53eca4c5b55f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905039"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams でのコール パークおよび保留解除

コール パークおよび保留解除は、ユーザーがクラウド内の Teams サービスで通話を保留にする機能です。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話を保留したユーザーまたは他のユーザーは、そのコードとサポートされているアプリやデバイスを使用して、通話を再開できます。 

コール パークを使用する一般的なシナリオには、次のようなものがあります。 

- 受付が、工場で働く人宛にかかってきた通話を保留にします。 次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。 通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。
- バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。 その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。
- サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。 エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。

> [!IMPORTANT]
> この機能を使用できるのは、Teams のみの展開モードだけです。 Teams 展開モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。

## <a name="license-required"></a>ライセンスが必要

通話を保留および解除するには、ユーザーがエンタープライズ VoIP ユーザーであり、管理者がユーザーにコール パーク ポリシーを付与する必要があります。 ライセンス モデルの詳細については、「[Microsoft Teams 用の Office 365 ライセンス](office-365-licensing.md)」を参照してください。

## <a name="call-park-and-retrieve-feature-availability"></a>コール パークおよび保留解除機能の可用性

コール パークおよび保留解除は現在、次のクライアントとデバイスでサポートされています。 (PSTN 接続の有無にかかわらず、Teams のみのモードでサポートされています。)

| 機能 | Teams デスクトップ | Teams Mac アプリ | Teams Web アプリ (Edge) |Teams モバイル iOS/Android アプリ | Teams IP 電話 | Skype for Business IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 通話を保留する | はい | はい | はい | はい | 近日対応予定| いいえ |
| 通話の保留を解除する | はい | はい | はい | はい | 近日対応予定| いいえ |
| 未解除通話のかけ直し | はい | はい | はい | はい | 近日対応予定| いいえ |

## <a name="configuring-call-park-and-retrieve"></a>コール パークおよび保留解除を構成する

コール パークおよび保留解除を構成するには管理者である必要があり、この機能は既定で無効になっています。 コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。 一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。 ユーザーのコール パークを構成したり、コール パーク ユーザー グループを作成したりするには、この下の「[コール パーク ポリシーを割り当てる](#assign-a-call-park-policy)」の手順に従ってください。

コール パークおよび保留解除機能の使用方法の詳細については、「[Teams で通話を保留する](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)」を参照してください。

### <a name="enable-a-call-park-policy"></a>コール パーク ポリシーを有効にする

コール パーク ポリシーを有効にするには、次の手順を実行します。

1. **[Microsoft Teams 管理センター]** > **[音声]** > **[コール パーク ポリシー]**.の順に移動します。
2. **[新しいポリシー]** を選択します。
3. ポリシーに名前を付け、次に **[コール パークを許可]** を **[オン]** に切り替えます。
4. **[保存]** を選択します。

### <a name="assign-a-call-park-policy"></a>コール パーク ポリシーを割り当てる

1 人以上のユーザーにコール パーク ポリシーを割り当てるには、次の手順を実行します。

1. **[Microsoft Teams 管理センター]** > **[音声]** > **[コール パーク ポリシー]**.の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選びます。
3. [**ユーザーを管理**] を選択します。
4. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、**[保存]** を選択します。
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>PowerShell を使用してコール パークおよび保留解除を構成する

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用して、コール パーク ポリシーを作成します。

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用して、コール パーク ポリシーを付与します。

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) を使用して既定の設定を変更するには、次のようにします。

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>トラブルシューティング

ユーザーが [パーク] または [取得] ボタンを表示できない場合: 

- ユーザーがコール パーク ポリシーを有効にしていることを確認します。 

ユーザーが通話の保留を解除しようとしても失敗した場合は、次の点を確認します:

- ユーザーが Teams クライアントまたは Teams が有効なデバイス/スマートフォンを使用していることを確認します
- グループ – ユーザーが、同じ Teams コール パーク ポリシーが割り当てられている、コール パーク グループのメンバーであるかを確認します。 
- アイランド モード – コール パークおよび保留解除は、Teams アイランド モードでは使用できません。
- 通話は既に保留解除または終了しています。

## <a name="more-information"></a>詳細情報

[Teams で通話を保留する](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。
