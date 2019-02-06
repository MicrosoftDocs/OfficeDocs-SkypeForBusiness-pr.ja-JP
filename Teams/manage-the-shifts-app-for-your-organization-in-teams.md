---
title: Microsoft Teams で組織のシフト アプリを管理する
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 1/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 設定し、組織内の先頭行の作業者のチームでシフトのアプリケーションを管理する方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 204dc5899a72b1bc1516441ca8654e7341f19942
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754528"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

> [!IMPORTANT]
> 効果的な 2019 年 10 月 1日マイクロソフトの StaffHub は廃止されます。 StaffHub 機能、マイクロソフトのチームに、スケジュールとタスクの管理などが進められています。 先頭行の作業者の他の機能ロール チームに時間の経過と共にします。 詳細については、[不要になったマイクロソフトの StaffHub](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0)を参照してください。  

## <a name="overview-of-shifts"></a>シフトの概要
マイクロソフトのチームでシフトのアプリケーションは、接続されているとの同期作業者の先頭行を保持します。モバイルを最初にビルド時間を迅速かつ効果的な管理とチームのための通信用です。 シフトでは、先頭行の作業者とマネージャーが自分のモバイル デバイスを使用してスケジュールを管理し、コミュニケーションをします。 

- マネージャーを作成するには、更新、およびチームのシフト スケジュールを管理します。 1 人のユーザーにメッセージを送信することができます (「は、算術、現場で」) または全体のチーム (「地域の GM が到着 20 分で」)。 ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。 
- 従業員の今後の変化を表示することができます 1 日に予定されている他のメンバーを参照してください、スワップまたは、shift キーを押しを提供し、オフ時間を要求する要求です。 

あるシフト現在サポートしていないゲスト ユーザーを知っているが重要です。 つまり、チームでは、来園者に追加するにはチームでゲスト アクセスが有効になっているときに shift キーを押しのスケジュールを使用します。 

## <a name="availability-of-shifts"></a>シフトの可用性

シフトは、例外の 2 つのチームを含むすべての Office 365 サブスクリプションで利用できます。 米国政府クラウド コミュニティ (GCC) および無料のチームは、例外があります。 シフトが Office 365 の米国政府機関では使用できません。 または、チームが製品を解放します。

チーム、チームを含む Office 365 サブスクリプションの一覧などのライセンスの詳細については、 [Office 365 は、チームのライセンス](Office-365-licensing.md)を参照してください。

## <a name="location-of-shifts-data"></a>シフトのデータの場所

北米、西ヨーロッパ、アジア太平洋地域でのデータ ・ センター内の Azure では、シフトのデータが格納されています。 データの保存場所の詳細について[がデータ](http://o365datacentermap.azurewebsites.net/)を参照してくださいでしょうか。

## <a name="set-up-shifts"></a>シフトを設定します

### <a name="enable-or-disable-shifts-in-your-organization"></a>有効にするか、組織内のシフトを無効にします。

シフトは、組織内のチームのすべてのユーザーに対して既定で有効になります。 オフにするか、Microsoft 365 の管理ページで、組織のアプリケーションを有効にします。

1. Office 365 管理者アカウントを使用して Microsoft 365 管理センターにサインインします。
2. **設定**に > **サービス & アドイン** > **マイクロソフトのチーム**です。 
3. **テナント全体の設定**、[**アプリケーション**を選択して [**既定のアプリケーション**をオフにしたり、**シフト**するチェック ボックスをオフにするか、アプリケーションを有効にするを選択します。 

    ![アプリケーションの既定のセクションのスクリーン ショット](media/firstline-worker-enable-disable-shifts.png "シフトのアプリケーションを含む、アプリケーションの一覧を示す Microsoft 365 管理センターで [アプリケーションの既定のセクションのスクリーン ショット")

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>チームに暗証番号 (pin) のシフトに FirstLineWorker アプリケーションの設定のポリシーを使用してください。

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

アプリケーション設定のポリシーを使用して、チームは、組織内のユーザーの最も重要なアプリケーションを強調表示をカスタマイズできます。 ポリシーの設定のアプリケーションが、アプリケーション バーに固定されている&mdash;チームのデスクトップ クライアント側にし、チームのモバイル クライアントの下部にあるバー&mdash;、迅速かつ容易にアクセスします。 
 
チームには、組み込み FirstLineWorker アプリケーションの設定ポリシー、組織内の先頭行の作業者に割り当てることができますが含まれています。 既定では、ポリシーには、アクティビティ、シフト、チャット、および通話のアプリケーションが含まれています。 

ポリシーを表示する、FirstLineWorker、マイクロソフトのチーム管理センターの左側のナビゲーションでは、**チームのアプリケーション**に移動 > **アプリケーションの設定のポリシー**です。

![マイクロソフトのチームの管理センターでは、FirstLineWorker アプリケーション セットアップ ポリシーのスクリーン ショット](media/firstline-worker-app-setup-policy.png "マイクロソフトのチームの管理センターでは、FirstLineWorker アプリケーション セットアップ ポリシーのスクリーン ショット")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>FirstLineWorker ポリシーを個々 のユーザーに割り当てます。

1. マイクロソフトのチーム管理センターの左側のナビゲーションでは、**ユーザー**に移動し、し、[ユーザー] をクリックします。
2. **割り当てポリシー**] の横にある [**編集**] をクリックします。
3. **チームのアプリケーション設定のポリシー**では、 **FirstLineWorker**を選択し、**保存**します。

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a>FirstLineWorker アプリケーションの設定のポリシーをグループ内のユーザーに割り当てる

グラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype への接続で、セキュリティ グループなど、グループ内のユーザーに FirstLineWorker アプリケーションの設定のポリシーを割り当てることができます。 PowerShell を使用して、チームを管理する詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。

この例では、contoso 社の先頭行のチームのグループ内のすべてのユーザーに FirstLineWorker アプリケーションの設定のポリシーを割り当てます。

> [!NOTE]
> [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスへの接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)の手順を実行して、まずグラフ モジュールの Azure Active Directory PowerShell およびビジネスの PowerShell モジュールの Skype に接続することを確認します。

特定のグループの GroupObjectId を取得します。
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
指定されたグループのメンバーを取得します。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
FirstLineWorker アプリケーションの設定のポリシーをグループ内のすべてのユーザーを割り当てます。
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
数によっては、グループ内のメンバーのこのコマンドは、実行するのに数分をかかる場合があります。

## <a name="related-topics"></a>関連トピック
- [シフトについては、先頭行の作業者と管理者](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)