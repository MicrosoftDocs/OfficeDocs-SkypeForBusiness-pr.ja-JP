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
ms.openlocfilehash: 692cf8500b47d903986542082c328b4a8be2237d
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2022
ms.locfileid: "63050913"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Bookings アプリを管理Microsoft Teams

Bookings アプリは、Microsoft Teamsと仮想の予定を簡単にスケジュールする方法を提供します。 たとえば、医療訪問、財務相談、面接、カスタマー サポート、教育オフィスの営業時間などです。 詳細については、「Virtual [visits with Teams and the Bookings app」を参照してください](expand-teams-across-your-org/bookings-virtual-visits.md)。

スケジューラは、1 回のエクスペリエンスから、複数の部署やスタッフの予定表を管理し、内部および外部の出席者との通信を管理できます。 仮想予定は、堅牢なビデオ会議Microsoft Teams会議を通じて開催されます。

> [!NOTE]
> Bookings アプリを Teams にインストールする必要があるのはスケジュール担当者だけです。 仮想予定を実施または参加するスタッフは、アプリを必要とします。 自分の予定表または予定表Outlook予定表Teams予約確認メールの [Teams 会議] リンクから、簡単に予定に参加できます。

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Bookings アプリを使用するための前提条件Teams

* メールボックスExchangeは、Exchange Online。 オンプレミスのExchange Serverメールボックスはサポートされていません。
* Microsoft Bookings は組織で利用できます。
* ユーザーは適切なライセンスを持っている。 Office 365 A3、A5、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3、Business Standard がサポートされています。
* Bookings アプリのすべてのユーザーと会議に参加しているすべてのスタッフは、会議のスケジュール設定をサポートTeamsライセンスを持っています。
* [ソフトウェアとブラウザーの前提条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams での Bookings の利用可能性

Microsoft Bookings app for Teamsデスクトップと Web で利用できます。 管理センターの [アプリ [] Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)、[アプリ **の** 管理] Teamsにあります。

### <a name="control-access-to-bookings-within-your-organization"></a>組織内の Bookings へのアクセスを制御する

Bookings アプリにアクセスできるユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。 Microsoft Bookings アプリを使用したり、アプリを無効にMicrosoft 365 管理センター。 または、Bookings アプリ ポリシーを作成して、選択したユーザーが Bookings カレンダーを作成できます。 「 [Microsoft Bookings にアクセスする」を参照してください](/microsoft-365/bookings/get-access)。

また、一部[のユーザー Teams Bookings アプリをピン留めするアプリ セットアップ ポリシーを作成することもできます](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>推奨される会議ポリシー設定

Bookings に最適なエクスペリエンスを有効にするには、組織内のすべてのユーザーをTeams許可し、そのポリシーをスタッフに割り当てる会議ポリシーを作成します。 このポリシーにより、スタッフは予定に自動的に参加し、外部出席者のロビー エクスペリエンスを有効にできます。 会議 [に自動的に参加を認める方法を参照してください](meeting-policies-participants-and-guests.md#automatically-admit-people)。

## <a name="optional-staff-approvals-setting"></a>オプションのスタッフ承認設定

Bookings がスケジュールの空き時間情報を共有する前や、他のユーザーと予定をスケジュールする前に、スタッフにオプトインを要求することができます。

この設定を有効にするには、[予約 **] Microsoft 365 管理センター**\>設定 **設定**\>、[**Bookings] を選択します**。

この設定をオンにすると、スタッフは予約予定表へのメンバーシップの承認を求めるメールを受信します。  

この機能は、Microsoft 365 および Office 365 のお客様に向けて世界中で段階的に展開されています。 すべてのオプションが環境でまだ使用できない場合は、すぐに確認してください。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Bookings メールボックスを設定するときに既定のドメインを変更する

Bookings メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメール ドメインが使用されます。 ただし、既定のドメインでは、外部の受信者に会議出席招待を送信するときに問題が発生する可能性があります。 たとえば、招待に迷惑メールのフラグが設定され、受信者の迷惑メール フォルダーに移動された場合、受信者に招待が表示されません。

Bookings メールボックスを作成する前に、既定のドメインを変更することをお勧めします。 ドメインに [関する FAQ を参照してください](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

Bookings メールボックスの作成後に既定のドメインを変更する必要がある場合は、PowerShell を使用します。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

メールボックスの設定コマンドレットに関する PowerShell [ドキュメントを参照](/powershell/module/exchange/mailboxes/set-mailbox) してください。

> [!NOTE]
> Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange と Exchange Online の間のメール フローを徹底的にテストすることをお勧めします。

## <a name="send-feedback"></a>フィードバックを送信する

以下に関するフィードバックをお寄せください。

* ユーザー エクスペリエンスまたは使いやすさ
* 機能のギャップまたは不足している機能
* バグや問題
  
フィードバックを送信するには、左側のナビゲーション バーの下部にある [ヘルプ] Teamsを選択し、[すべての問題について問題を報告 **する**] **を** 選択します。 Bookings に関する問題を簡単に特定できるよう、フィードバック レポートの先頭に「Bookings」に関するフィードバックを送信する必要があります。

## <a name="related-articles"></a>関連記事

[モバイル ブラウザーで仮想アクセスTeamsの参加エクスペリエンスを管理する](expand-teams-across-your-org/mobile-browser-join.md)


  [エンド ユーザー向け Bookings ドキュメント](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
