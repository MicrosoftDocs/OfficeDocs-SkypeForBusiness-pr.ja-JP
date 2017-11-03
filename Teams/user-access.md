---
title: "Microsoft Teams へのユーザー アクセスを管理する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "ユーザーごとにユーザーレベル アクセスを有効または無効にする方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 79dbf55d14b1866a30b5396bb5668a28df95946a
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2017
---
<a name="manage-user-access-to-microsoft-teams"></a>Microsoft Teams へのユーザー アクセスを管理する
=====================================

Microsoft Teams へのユーザーレベルのアクセスは、Microsoft Teams 製品ライセンスの割り当てと削除によってユーザーごとに有効化または無効化することができます。

現時点では、ライセンス以外の手段を使用して、個々のユーザーの Microsoft Teams または Microsoft Teams 機能のサブセットをオンまたはオフにするポリシー オプションはありません。

| | |
|---------|---------|
|![注意アイコン。](media/Manage_user_access_to_Microsoft_Teams_image1.png)<br></br>注意 |会社のすべてのユーザーに対して Microsoft Teams を有効にすることをお勧めします。そうすることで、プロジェクトやその他の動的なイニシアチブで組織的にチームを編成することが可能になります。パイロットを行う場合でも、すべてのユーザーで Microsoft Teams を有効のままにしておき、パイロット グループのユーザーに対してのみ通信を行うことができます。 |

Microsoft Teams のユーザーレベルのライセンスは Office 365 管理センターのユーザー管理インターフェースから直接行います。管理者は、新しいユーザー アカウントを作成するときに新しいユーザーにライセンスを割り当てたり、既存のアカウントのユーザーにライセンスを割り当てることができます。Microsoft Teams のライセンスを管理する管理者は Office 365 グローバル管理またはユーザー管理の管理者の権限が必要です。

E3 または E5 といったライセンス SKU をユーザーに割り当てる場合、Microsoft Teams ライセンスが自動的に割り当てられ、そのユーザーには Microsoft Teams が有効化されます。管理者はすべての Office 365 サービスとライセンスを細かく制御できます。特定のユーザーまたはグループの Microsoft Teams ライセンスを有効または無効にすることができます。

![Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Microsoft Teams のユーザー ライセンスはいつでも無効にできます。いったん無効にすると、そのユーザーは Microsoft Teams にアクセスできなくなり、Office 365 アプリのランチャーやホームページで Microsoft Teams を表示できなくなります。

![Microsoft Teams が選択されていることを示す Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

Office 365 の管理者は、Office 365 管理センターに加えて、Office 365 PowerShell を使用してもライセンスの割り当てと割り当て解除を行うことができます。ユーザーにライセンスを割り当てるには、次の構文を使用します。

Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"

次の例では、litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンス プランのライセンスを、ライセンスのないユーザー belindan@litwareinc.com に割り当てます。

Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"

詳細と例については、「[*Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる*](https://go.microsoft.com/fwlink/?linkid=855755)」をご覧ください。

既存のユーザー アカウントからライセンスを割り当て解除するには、次の構文を使用します。

Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"

次の例では、litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンスを、ユーザー アカウントBelindaN@litwareinc.com から割り当て解除します。

Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"

詳細と例については、「[*Office 365 PowerShell を使用してライセンスをユーザー アカウントから割り当て解除する*](https://go.microsoft.com/fwlink/?linkid=855756)」をご覧ください。

| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |判断ポイント         |<ul><li>組織全体での Microsoft Teams への関与を促進するための計画を教えてください (パイロットまたはオープン)。</li></ul>         |
|![次のステップ アイコン。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |次のステップ         |<ul><li>閉じられたパイロットで関与促進を行う場合は、ライセンスまたは対象を絞った通信のいずれかの手段で実施するかを決定します。</li><li>この決定に応じて、Microsoft Teams へのアクセスが許可されているユーザーがパイロット ユーザーのみであることを確認する手順を行います (必要な場合)。</li><li>次の資料を使用して、Microsoft Teams にアクセスできる (またはアクセスできない) ユーザー向けのガイドラインを文書化します。</li></ul>         |
