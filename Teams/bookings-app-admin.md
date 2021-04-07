---
title: Microsoft Teams と Bookings アプリを使用した仮想訪問
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
description: Microsoft Teams と、Bookings アプリを使用した仮想訪問
ms.openlocfilehash: 7cb948e020d27ccee396aebb8d1b36b022160a75
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598606"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams と Bookings アプリを使用した仮想訪問

Microsoft Teams の Bookings アプリでは、医療訪問、財務相談、インタビュー、カスタマー サポート、教育用のオフィス時間など、対面および仮想的な予定を簡単にスケジュールできます。

スケジュール担当者は、1 つの操作環境から、複数の部門とスタッフの予定表、および組織内外の出席者との通信を管理できます。 仮想予定自体は、強力なビデオ会議機能を提供する Microsoft Teams 会議を介して開催されます。

> [!NOTE]
> Bookings アプリを Teams にインストールする必要があるのはスケジュール担当者だけです。 仮想予定を実施または参加するスタッフは、アプリを必要としません。 Outlook または Teams の予定表から、または予約確認メールのリンクから、予定に参加できます。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Teams で Bookings アプリを使用するための前提条件

- Exchange メールボックスは Exchange Online にある必要があります。 オンプレミスの Exchange Server メールボックスはサポートされていません。

- Microsoft Bookings を組織で有効にしている必要があります。

- ユーザーは、適切なライセンスを持っている必要があります。 Office 365 A3、A5、E3、E5 だけでなく、Microsoft 365 Business Standard、A3、A5、E3、E5 もサポートされています。

- Bookings アプリのすべてのユーザーと会議に参加するすべてのスタッフは、Teams 会議のスケジュールをサポートするライセンスを持っている必要があります。

- システムは、すべての[ソフトウェアとブラウザーの前提条件](hardware-requirements-for-the-teams-app.md)を満たす必要があります。

## <a name="availability-of-bookings-in-teams"></a>Teams での Bookings の利用可能性

Teams 用の Microsoft Bookings アプリは、デスクトップと Web で利用できます。 これは、[Microsoft Teams 内の アプリ](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)と Teams 管理センターの **[アプリの管理]** で見つかります。

### <a name="control-access-to-bookings-within-your-organization"></a>組織内の Bookings へのアクセスを制御する

Bookings アプリにアクセスできるユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。 Microsoft 365 管理センターで Microsoft Bookings をオンまたはオフにする方法、および選択したユーザーが Bookings の予定表を作成できるようにする Bookings アプリ ポリシーを作成する方法については、「[Microsoft Bookings にアクセスする](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)」を参照してください。 [Teams アプリ ポリシーを作成して、一部のユーザーに Bookings アプリをピン留めする方法](teams-app-setup-policies.md)も参照してください。

## <a name="recommended-meeting-policy-settings"></a>推奨される会議ポリシーの設定

Bookings で最高のエクスペリエンスを実現するには、スタッフ会議ポリシーを作成して、**組織内のすべてのユーザー** を自動的に承認するようにします。 これにより、スタッフは予定に自動的に参加できるようになり、外部出席者のロビー エクスペリエンスを有効にすることができます。 詳細については、「[会議へのユーザーの参加を自動的に許可する](meeting-policies-participants-and-guests.md#automatically-admit-people)」を参照してください。

### <a name="optional-staff-approvals-setting"></a>オプションのスタッフ承認設定

追加のプライバシー設定として、スケジュールの空き時間情報が Bookings を通じて共有される前や、予定を予約する前に、スタッフに参加を要求することを選択できます。  

この設定を有効にするには、**[Microsoft 365 管理センター]** \> **[設定]** \> **[設定]** に移動し、**[Bookings]** を選択します。

この設定をオンにすると、予約予定表のメンバーシップを承認するように求めるメールがスタッフに送信されます。  

この機能は、Microsoft 365 および Office 365 のお客様に向けて世界中で段階的に展開されています。 ご使用の環境ですべてのオプションがまだ利用できない場合は、しばらくしてからもう一度お試しください。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Bookings メールボックスのセットアップ時に既定のドメインを変更する

Bookings メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメール ドメインが使用されます。 ただし、それにより外部の受信者に会議出席招待を送信するときに問題が発生する可能性があります。具体的には、招待に迷惑メールのフラグが設定され、受信者の迷惑メール フォルダーに移動される可能性があり、その場合、受信者はその招待を表示しない可能性があります。

Bookings メールボックスを作成する前に、既定のドメインを変更することをお勧めします。 これを行う方法について詳しくは、「[ドメインに関する FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)」を参照してください。

Bookings メールボックスが既に作成された後に既定のドメインを変更する必要がある場合は、PowerShell で変更できます。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

詳細については、「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」コマンドレットの PowerShell ドキュメントを参照してください。

> [!NOTE]
> Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange と Exchange Online 間のメール フローを十分にテストすることをお勧めします。

## <a name="sending-feedback"></a>フィードバックの送信

以下に関するフィードバックをお寄せください。

  - ユーザー エクスペリエンスまたは使いやすさ
  - 機能のギャップまたは不足している機能
  - バグや問題
  
フィードバックを送信するには、Teams の左側のナビゲーション バーの下部にある **[ヘルプ]** ボタンをクリックし、**すべて** の問題に関するフィードバック用の **[問題の報告]** をクリックします。 フィードバック レポートの先頭に、"Bookings" に関するフィードバックであることを明記してください。それにより、Bookings に関する問題を簡単に識別することができます。

## <a name="related-topics"></a>関連トピック


  [エンド ユーザー向け Bookings ドキュメント](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)