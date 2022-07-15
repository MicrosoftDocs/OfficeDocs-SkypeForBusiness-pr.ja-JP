---
title: Microsoft Teams で Bookings アプリを管理する
author: LanaChin
ms.author: v-lanachin
manager: samanro
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
description: 組織内のユーザー向けに Teams で Bookings アプリを管理する方法について説明します。
ms.openlocfilehash: f11739784dcb9897bf9a3fcbffdadc8aea00d3e0
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819292"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Microsoft Teams で Bookings アプリを管理する

Microsoft Teams の Bookings アプリは、対人および仮想の予定を簡単にスケジュールする方法を提供します。 たとえば、医療訪問、財務相談、面接、カスタマー サポート、教育の営業時間などです。 詳細については、「 [Teams と Bookings アプリを使用した仮想予定」を](/microsoft-365/frontline/bookings-virtual-visits)参照してください。

スケジューラは、1 つのエクスペリエンスから、複数の部署とスタッフの予定表と内部および外部の出席者との通信を管理できます。 仮想予定は、堅牢なビデオ会議機能を提供する Microsoft Teams 会議を介して開催されます。

> [!NOTE]
> Bookings アプリを Teams にインストールする必要があるのはスケジュール担当者だけです。 仮想予定を実施または参加するスタッフは、アプリを必要としません。 Outlook または Teams の予定表から、または予約確認メールの Teams 会議リンクから、予定に参加できます。

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Teams で Bookings アプリを使用するための前提条件

* Exchange メールボックスはExchange Onlineにあります。 オンプレミスのExchange Server メールボックスはサポートされていません。
* Microsoft Bookingsは組織で使用できます。
* ユーザーは適切なライセンスを持っています。 Office 365 A3、A5、E1、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3、ビジネス 標準がサポートされています。
* Bookings アプリのすべてのユーザーと会議に参加しているすべてのスタッフは、Teams 会議のスケジュール設定をサポートするライセンスを持っています。
* [ソフトウェアとブラウザーの前提条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams での Bookings の利用可能性

Microsoft Bookings Teams 用アプリは、デスクトップと Web で利用できます。 Teams の [[アプリ] と [Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 管理センター] の **[アプリの管理** ] にあります。

### <a name="control-access-to-bookings-within-your-organization"></a>組織内の Bookings へのアクセスを制御する

Bookings アプリにアクセスできるユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。 Microsoft Bookingsアプリを使用できるようにしたり、Microsoft 365 管理センターから無効にしたりできます。 または、Bookings アプリ ポリシーを作成して、選択したユーザーが Bookings 予定表を作成できるようにします。 [Microsoft Bookingsへのアクセス権の取得に関する](/microsoft-365/bookings/get-access)をご覧ください。

Teams [アプリセットアップ ポリシーを作成して、選択したユーザーの Bookings アプリをピン留め](teams-app-setup-policies.md)することもできます。

## <a name="recommended-meeting-policy-settings"></a>推奨される会議ポリシー設定

Bookings に最適なエクスペリエンスを実現するには、 **組織内のすべてのユーザー** を自動的に許可し、ポリシーをスタッフに割り当てる Teams 会議ポリシーを作成します。 このポリシーにより、スタッフは予定に自動的に参加し、外部出席者のロビー エクスペリエンスを有効にすることができます。 [会議に自動的にユーザーを許可する方法について説明します](meeting-policies-participants-and-guests.md#automatically-admit-people)。

会議ポリシーの詳細については、「 [Teams での会議ポリシーの管理](meeting-policies-in-teams.md) 」と [「Teams での会議ポリシーと会議の有効期限」を参照してください](meeting-expiration.md)。

## <a name="optional-staff-approvals-setting"></a>オプションのスタッフ承認設定

Bookings がスケジュールの可用性情報を共有する前に、他のユーザーが予定をスケジュールする前に、スタッフにオプトインを要求できます。

この設定を有効にするには、[**Microsoft 365 管理センター** \> **設定]** \> に移動し、[**Bookings**] を選択します。

この設定をオンにすると、スタッフは予約カレンダーへのメンバーシップを承認するように要求された電子メールを受け取ります。  

この機能は、Microsoft 365 および Office 365 のお客様に向けて世界中で段階的に展開されています。 ご利用の環境でまだすべてのオプションを使用できない場合は、すぐにご確認ください。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Bookings メールボックスを設定するときに既定のドメインを変更する

Bookings メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメール ドメインが使用されます。 ただし、既定のドメインでは、会議出席依頼を外部の受信者に送信するときに問題が発生する可能性があります。 たとえば、招待のフラグがスパムとして設定され、受信者の迷惑メール フォルダーに移動された場合、受信者に招待が表示されない可能性があります。

Bookings メールボックスを作成する前に、既定のドメインを変更することをお勧めします。 ドメインに [関する FAQ を参照してください](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

Bookings メールボックスの作成後に既定のドメインを変更する必要がある場合は、PowerShell を使用します。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

メールボックスコマンドレットの [設定](/powershell/module/exchange/mailboxes/set-mailbox) に関する PowerShell のドキュメントを参照してください。

> [!NOTE]
> Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange とExchange Onlineの間のメール フローを十分にテストすることをお勧めします。

## <a name="send-feedback"></a>フィードバックを送信する

以下に関するフィードバックをお寄せください。

* ユーザー エクスペリエンスまたは使いやすさ
* 機能のギャップまたは不足している機能
* バグや問題
  
フィードバックを送信するには、Teams の左側のナビゲーション バーの下部にある **[ヘルプ**] オプションを選択し、[**すべての****問題に関する問題の報告**] を選択します。 フィードバック レポートの冒頭で、"Bookings" に関するフィードバックを送信していることを示して、Bookings の問題を簡単に特定できるようにします。

## <a name="related-articles"></a>関連記事

[ブラウザーで Teams 仮想予定の参加エクスペリエンスを管理する](/microsoft-365/frontline/browser-join)


  [エンド ユーザー向け Bookings ドキュメント](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
