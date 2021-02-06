---
title: Microsoft Teams と Bookings アプリを使用した仮想アクセス
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams と Bookings アプリでの仮想アクセス
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125750"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams と Bookings アプリを使用した仮想アクセス

Microsoft Teams の Bookings アプリでは、医療訪問、財務相談、インタビュー、カスタマー サポート、教育用のオフィス時間など、対面および仮想的な予定を簡単にスケジュールできます。

スケジューラーは、1 つの操作環境から、複数の部門予定表とスタッフ 予定表、および内部および外部の出席者との通信を管理できます。 仮想予定自体は、強力なビデオ会議機能を提供する Microsoft Teams 会議を介して開催されます。

> [!NOTE]
> スケジューラーだけが、Bookings アプリを Teams にインストールする必要があります。 仮想予定を実施または参加しているスタッフは、アプリを必要とします。 Outlook または Teams の予定表から、または予約確認メールのリンクから、予定に参加できます。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Teams で Bookings アプリを使用するための前提条件

- Exchange メールボックスは Exchange Online にある必要があります。 オンプレミスのExchange Serverメールボックスはサポートされていません。

- Microsoft Bookings を組織で有効にしている必要があります。

- ユーザーは適切なライセンスが必要です。 Office 365 A3、A5、E3、E5 だけでなく、Microsoft 365 Business Standard、A3、A5、E3、E5 もサポートされています。

- Bookings アプリのすべてのユーザーと会議に参加しているすべてのスタッフは、Teams 会議のスケジュールをサポートするライセンスを持っている必要があります。

- システムは、すべてのソフトウェアと [ブラウザーの前提条件を満たす必要があります](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams での Bookings の可用性

Microsoft Bookings App for Teams は、デスクトップと Web で利用できます。 これは、Microsoft Teams 内の [アプリと Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 管理センターの **[** アプリの管理] にあります。

### <a name="control-access-to-bookings-within-your-organization"></a>組織内の Bookings へのアクセスを制御する

Bookings アプリにアクセスできるユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。 Microsoft 365 管理センターで Microsoft Bookings をオンまたはオフにする方法、および選択したユーザーが Bookings の予定表を作成できる Bookings アプリ ポリシーを作成する方法については [、「Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)にアクセスする」を参照してください。 Teams アプリ ポリシーを作成して、一部のユーザーに Bookings アプリをピン [留めする方法も学習できます](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>推奨される会議ポリシーの設定

Bookings で最高のエクスペリエンスを有効にするには、組織内のすべてのユーザーを自動的に参加を認めるスタッフ会議ポリシー **を作成します**。 これにより、スタッフは予定に自動的に参加し、外部出席者のロビーエクスペリエンスを有効にできます。 会議へのユーザーの自動参加 [を認める方法の詳細については、以下を参照してください](meeting-policies-in-teams.md#automatically-admit-people)。

### <a name="optional-staff-approvals-setting"></a>オプションのスタッフ承認設定

追加のプライバシー設定として、スケジュールの空き時間情報が Bookings を通じて共有される前や、予定を予約する前に、スタッフに参加を要求することを選択できます。  

この設定を有効にするには **、Microsoft 365 管理** センターの [設定] に移動し \>  \> **、[Bookings] を選択します**。

この設定をオンにすると、予約予定表のメンバーシップを承認するように求めるメールがスタッフに送信されます。  

この機能は、Microsoft 365 および 365 ユーザー向Office段階的に展開されています。 環境でまだ利用できないオプションがある場合は、間もなくご確認ください。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Bookings メールボックスをセットアップするときに既定のドメインを変更する

Bookings メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメール ドメインが使用されます。 ただし、外部の受信者に会議出席招待を送信するときに問題が発生する可能性があります。招待に迷惑メールのフラグが設定され、受信者の迷惑メール フォルダーに移動された場合、受信者に招待が表示されません。

Bookings メールボックスを作成する前に、既定のドメインを変更することをお勧めします。 この方法については、ドメインに関する [FAQ を参照してください](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

Bookings メールボックスが既に作成された後に既定のドメインを変更する必要がある場合は、PowerShell で変更できます。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

詳細については [、Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) コマンドレットの PowerShell ドキュメントを参照してください。

> [!NOTE]
> Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange と Exchange Online の間のメール フローを徹底的にテストすることをお勧めします。

## <a name="sending-feedback"></a>フィードバックの送信

以下に関するフィードバックをお寄せください。

  - ユーザー エクスペリエンスまたは使いやすさ
  - 機能のギャップまたは不足している機能
  - バグや問題
  
フィードバックを送信するには、Teamsの左側のナビゲーション バーの下部にある [ヘルプ]ボタンをクリックし、[すべての問題に関する問題の報告]**をクリックします**。 フィードバック レポートの先頭に、Bookings に関するフィードバックを送信すると、Bookings の問題を簡単に特定できます。

## <a name="related-topics"></a>関連項目

[エンド ユーザー向け Bookings ドキュメント](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
