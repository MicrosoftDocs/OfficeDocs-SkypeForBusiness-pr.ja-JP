---
title: Bookings アプリを管理Microsoft Teams
author: dmaguire
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 組織内のユーザー向け Bookings アプリを Teams管理する方法について学習します。
ms.openlocfilehash: 147089c51ebc6d3e5eb6bf567579c9aa7fc5f2ce
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763731"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Bookings アプリを管理Microsoft Teams

Microsoft Teams の Bookings アプリでは、医療訪問、財務相談、インタビュー、カスタマー サポート、教育用のオフィス時間など、対面および仮想的な予定を簡単にスケジュールできます。 詳細については、「Virtual [Visits with Teams と Bookings app」を参照してください](expand-teams-across-your-org/bookings-virtual-visits.md)。

スケジュール担当者は、1 つの操作環境から、複数の部門とスタッフの予定表、および組織内外の出席者との通信を管理できます。 仮想予定自体は、堅牢なビデオ会議機能Microsoft Teams会議を通じて開催されます。

> [!NOTE]
> Bookings アプリを Teams にインストールする必要があるのはスケジュール担当者だけです。 仮想予定を実施または参加するスタッフは、アプリを必要とします。 予約の確認メールで、Outlook予定表Teams、または Teams 会議のリンクから、予定に参加できます。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Teams で Bookings アプリを使用するための前提条件

- Exchange メールボックスは Exchange Online にある必要があります。 オンプレミスのExchange Serverメールボックスはサポートされていません。

- 組織で Microsoft Bookings が有効になっている必要があります。

- ユーザーは、適切なライセンスを持っている必要があります。 Office 365 A3、A5、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3、Business Standard がサポートされています。

- Bookings アプリのすべてのユーザーと会議に参加しているすべてのスタッフは、会議のスケジュール設定をサポートするライセンスTeams必要があります。

- システムは、すべての[ソフトウェアとブラウザーの前提条件](hardware-requirements-for-the-teams-app.md)を満たす必要があります。

## <a name="availability-of-bookings-in-teams"></a>Teams での Bookings の利用可能性

Microsoft Bookings app for Teamsデスクトップおよび Web で利用できます。 これは、管理センターの [[アプリ] Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)の **[アプリの管理**] Teamsにあります。

### <a name="control-access-to-bookings-within-your-organization"></a>組織内の Bookings へのアクセスを制御する

Bookings アプリにアクセスできるユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。

Microsoft 365 管理センター で Microsoft Bookings のオンとオフを切り替え、選択したユーザーが Bookings カレンダーを作成できる Bookings アプリ ポリシーを作成する方法については、「[Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce) にアクセスする」を参照してください。

また、一部[のユーザー Teams Bookings アプリをピン留めするアプリ セットアップ ポリシーを作成することもできます](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>推奨される会議ポリシー設定

Bookings に最適なエクスペリエンスを有効にするには、組織内のすべてのユーザーをTeams許可し、そのポリシーをスタッフに割り当てる会議ポリシーを作成します。 これにより、スタッフは予定に自動的に参加し、外部の出席者のロビー エクスペリエンスを有効にできます。 会議へのユーザーの自動参加を [認める方法の詳細については、次のリンクを参照してください](meeting-policies-participants-and-guests.md#automatically-admit-people)。

## <a name="optional-staff-approvals-setting"></a>オプションのスタッフ承認設定

追加のプライバシー設定として、スケジュールの空き時間情報が Bookings を通じて共有される前や、予定を予約する前に、スタッフに参加を要求することを選択できます。  

この設定を有効にするには、[**予約] Microsoft 365 管理センター**\>設定 **設定**\>、[**Bookings] を選択します**。

この設定をオンにすると、スタッフは予約予定表のメンバーシップを承認するように求めるメールを受信します。  

この機能は、Microsoft 365 および Office 365 のお客様に向けて世界中で段階的に展開されています。 すべてのオプションが環境でまだ使用できない場合は、すぐに確認してください。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Bookings メールボックスのセットアップ時に既定のドメインを変更する

Bookings メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメール ドメインが使用されます。 ただし、それにより外部の受信者に会議出席招待を送信するときに問題が発生する可能性があります。具体的には、招待に迷惑メールのフラグが設定され、受信者の迷惑メール フォルダーに移動される可能性があり、その場合、受信者はその招待を表示しない可能性があります。

Bookings メールボックスを作成する前に、既定のドメインを変更することをお勧めします。 これを行う方法について詳しくは、「[ドメインに関する FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)」を参照してください。

Bookings メールボックスが既に作成された後に既定のドメインを変更する必要がある場合は、PowerShell で変更できます。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

詳細については、「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」コマンドレットの PowerShell ドキュメントを参照してください。

> [!NOTE]
> Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange と Exchange Online の間のメール フローを徹底的にテストすることをお勧めします。

## <a name="sending-feedback"></a>フィードバックの送信

以下に関するフィードバックをお寄せください。

  - ユーザー エクスペリエンスまたは使いやすさ
  - 機能のギャップまたは不足している機能
  - バグや問題
  
フィードバックを送信するには、左側のナビゲーション バーの下部にある [ヘルプ] Teamsを選択し、[すべての問題について問題を報告する **] を選択** します。 Bookings に関する問題を簡単に特定できるよう、フィードバック レポートの先頭に「Bookings」に関するフィードバックを送信する必要があります。

## <a name="related-articles"></a>関連記事

[モバイル ブラウザーで仮想アクセスTeamsの参加エクスペリエンスを管理する](expand-teams-across-your-org/mobile-browser-join.md)


  [エンド ユーザー向け Bookings ドキュメント](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
