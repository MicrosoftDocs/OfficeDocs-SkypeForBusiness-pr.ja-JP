---
title: Microsoft Teams でのコール パークおよび保留解除
author: CarolynRowe
ms.author: crowe
manager: serdars
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: コール パークを使用して取得し、Microsoft Teams で通話を保留にする方法について説明します。
ms.openlocfilehash: c541f92b265d5794df4513eb0cda5d2ff2969f20
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614240"
---
# <a name="configure-call-park-and-retrieve"></a>コール パークを構成して取得する

コール パークと取得を使用すると、ユーザーは通話を保留にできます。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話をパークしたユーザーまたは他のユーザーは、サポートされているアプリまたはデバイスでそのコードを使用して通話を取得できます。 (詳細については、「 [Teams で通話をパークする](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)」を参照してください)。

コール パークを使用する一般的なシナリオには、次のようなものがあります。

- 受付が、工場で働く人宛にかかってきた通話を保留にします。 次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。 通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。

- バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。 その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。

- サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。 専門家が Teams クライアントにコードを入力して、通話を取得します。

通話をパークして取得するには、ユーザーがエンタープライズ VoIP ユーザーでなければならず、コール パーク ポリシーに含める必要があります。

既定では、通話ピックアップ番号の範囲は 10 ~ 99 です。 10 ~ 9999 の間で独自のカスタム範囲を作成することもできます。 最初にパークされた呼び出しは、範囲の開始 (たとえば 10) のピックアップ コードがレンダリングされます。 次にパークされた呼び出しでは、ピックアップ コードが 1 ずつインクリメントされてレンダリングされます。つまり、11 など、範囲の末尾がピックアップ コードとしてレンダリングされるまでです。 その後、レンダリングされたピックアップ コードは、範囲の先頭からもう一度やり直します。 

タイムアウトは、パークされた呼び出しがピックアップされていないときに呼び出し元に戻るまで待機する秒数として指定できます。 指定できる範囲は 120 ~ 1800 秒で、既定値は 300 秒です。

コール パークを構成して取得するには、Teams 管理者である必要があります。 既定では無効になっています。 これをユーザーに対して有効にし、コール パーク ポリシーを使用してユーザー グループを作成できます。 一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。

> [!NOTE]
> コール パークと取得は、 [Teams のみ展開モード](teams-and-skypeforbusiness-coexistence-and-interoperability.md)でのみ使用できます。 Skype for Business IP フォンではサポートされていません。

コール パークを構成し、Teams 管理センターを使用するか、PowerShell を使用して取得できます。

## <a name="use-teams-admin-center"></a>Teams 管理センターを使用する

新しいコール パーク ポリシー インスタンスを作成するには:

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **音声** > **通話パーク ポリシー** に移動します。

2. [ **ポリシーの管理** ] タブで、[ **追加**] をクリックします。

3. ポリシーに名前を付け、[ **コール パークを許可する** ] を **[オン]** に切り替えます。

4. 必要に応じて、範囲とパーク タイムアウトを変更します。

5. **[保存]** を選択します。

ポリシーを編集するには、一覧でポリシーを選択し、[ **編集]** をクリックします。

ポリシーを機能させるには、ユーザーに割り当てる必要があります。 [ポリシーは、ユーザーに個別に割り当てるか、グループに](assign-policies-users-and-groups.md)割り当てることができます。

グループにコール パーク ポリシーを割り当てるには:

1. [ **コール パーク ポリシー** ] ページの [ **グループ ポリシーの割り当て** ] タブで、[ **グループの追加**] をクリックします。

2. 使用するグループを検索し、[ **追加**] をクリックします。

3. 他のグループ割り当てと比較してランクを選択します。

4. [ **ポリシーの選択]** で、このグループを割り当てるポリシーを選択します。

5. **[適用]** を選択します。

## <a name="use-powershell"></a>PowerShell を使用する

PowerShell を使用してコール パークを管理し、ポリシーを取得するには、次の Teams PowerShell モジュール コマンドレットを使用します。

- [New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

- [Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

- [Get-CsTeamsCallParkPolicy](/powershell/module/skype/get-csteamscallparkpolicy)

- [Remove-CsTeamsCallParkPolicy](/powershell/module/skype/remove-csteamscallparkpolicy)

- [Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)

### <a name="examples"></a>例

#### <a name="new-custom-call-park-policy"></a>新しいカスタム コール パーク ポリシー

次の例では、500 から 1500 までのピックアップ番号を生成するカスタム コール パーク ポリシーを作成し、パークされた呼び出しが応答しない場合は 600 秒後にパークを呼び出します。

```powershell
PS C:\> New-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $true -PickupRangeStart 500 -PickupRangeEnd 1500 -ParkTimeoutSeconds 600
```

#### <a name="change-a-call-park-policy"></a>コール パーク ポリシーを変更する

次の例では、コール パーク ポリシーを無効にします。

```powershell
PS C:\> Set-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $false
```

#### <a name="grant-a-call-park-policy-to-a-user"></a>コール パーク ポリシーをユーザーに付与する

次の例では、コール パーク ポリシーをユーザーに付与します。

```powershell
PS C:\> Grant-CsTeamsCallParkPolicy -PolicyName "SalesPolicy" -Identity Ken.Myer@contoso.com
```

#### <a name="remove-a-call-park-policy"></a>コール パーク ポリシーを削除する

次の例では、コール パーク ポリシーを削除します。

```powershell
PS C:\> Remove-CsTeamsCallParkPolicy -Identity "SalesPolicy"
```

## <a name="related-topics"></a>関連項目

[Teams で通話をパークする](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)

