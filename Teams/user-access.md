---
title: "Microsoft チームのユーザー アクセスを管理します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "有効にする、ユーザーごとにユーザー レベルのアクセスを無効にする方法について説明します。"
ms.openlocfilehash: 66ec29077b83b799c85acce1b5869b82fb0b83f7
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="manage-user-access-to-microsoft-teams"></a>Microsoft チームのユーザー アクセスを管理します。
=====================================

ユーザー レベルで Microsoft チームへのアクセスできるユーザーごとに無効の割り当てまたはチームの Microsoft 製品のライセンスを削除してできます。

現時点では、Microsoft チーム、または Microsoft チーム機能のサブセットをオンまたはオフにライセンスの外部で個別のユーザー レベルのポリシー オプションはありません。



> [!NOTE]
>Microsoft チームが有効であるすべてのユーザー、会社のチーム プロジェクトおよび他の動的な計画の実施形成するようにすることをお勧めします。する場合でも、パイロットこともあります、すべてのユーザーを有効になっている Microsoft チームを残してのみパイロット ユーザー グループへの通信を対象にするおくと便利です。

Microsoft チームのユーザー レベルのライセンスについては、Office 365 管理センターのユーザーの管理インターフェイスを使用して直接管理されます。管理者は、新しいユーザー アカウントを作成するときに新しいユーザー、または既存のアカウントを持つユーザーにライセンスを割り当てることができます。管理者は、Microsoft チームのライセンスを管理する Office 365 のグローバル管理者またはユーザー管理の管理者権限が必要です。

E3 など E5 SKU がユーザーに割り当てられているライセンスを Microsoft チーム ライセンスが自動的に割り当てられているし、ユーザーが Microsoft チーム用に有効にします。管理者がすべての Office 365 サービスと、ライセンスを細かく制御を設定して、特定のユーザーまたはユーザーのグループの Microsoft チーム ライセンスを有効または無効になっていることができます。

![Office 365 管理センターのライセンス] セクションの製品のスクリーン ショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Microsoft チームのユーザー ライセンスは、いつでも無効にすることができます。ライセンスを無効にすると、ユーザーが Microsoft チームにアクセスできませんし、ユーザーは、Office 365 アプリ起動ツールとホーム ページで Microsoft チームを表示できなきます。

![Office 365 管理センターで、選択されている Microsoft チームが表示されているライセンス] セクションの製品のスクリーン ショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

Office 365 管理センターではなく、Office 365 の管理者は Office 365 PowerShell を割り当てるライセンスを削除しても使用できます。ライセンスをユーザーに割り当てるには、次の構文を使用します。

セット MsolUserLicense UserPrincipalName"\<アカウント\>"- AddLicenses"\<AccountSkuId\>"

次の例では、ライセンスのないユーザー belindan@litwareinc.com に litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンス プランからのライセンスを割り当てます。

設定 MsolUserLicense-UserPrincipalName"belindan@litwareinc.com"- AddLicenses"litwareinc:ENTERPRISEPACK"

その他の詳細および例では、 [*Office 365 PowerShell でのユーザー アカウントにライセンスを割り当てる*](https://go.microsoft.com/fwlink/?linkid=855755)を参照してください。

既存のユーザー アカウントからライセンスを削除するには、次の構文を使用します。

セット MsolUserLicense UserPrincipalName\<アカウント\>- RemoveLicenses"\<AccountSkuId1\>「,」\<AccountSkuId2\>"

次の例では、ユーザー アカウント BelindaN@litwareinc.com から litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンスを削除します。

設定 MsolUserLicense-UserPrincipalName belindan@litwareinc.com - RemoveLicenses"litwareinc:ENTERPRISEPACK"

その他の詳細および例では、 [*office がユーザーのアカウントから 365 PowerShell ライセンスを削除する*](https://go.microsoft.com/fwlink/?linkid=855756)をご覧ください。

| | | |
|---------|---------|---------|
|![判断するポイントをタップします。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |判断するポイント         |<ul><li>Microsoft チーム オンボーディングの組織の計画は、組織全体で何ですか。 テスト導入期間 (開く)</li></ul>         |
|![次の手順をタップします。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |次のステップ         |<ul><li>閉じたパイロットを介してオンボーディングことに決めたかどうかライセンス、または対象のコミュニケーションを通じて実行する場合。</li><li>意思決定、によってかかるのみパイロット (必要な場合) は、マイクロソフトのチームをアクセスを許可されているユーザーの手順を実行していることを確認します。</li><li>ドキュメントのユーザーのユーザーが (または表示されません) のガイドラインは、次の Microsoft チームにアクセスします。</li></ul>         |
