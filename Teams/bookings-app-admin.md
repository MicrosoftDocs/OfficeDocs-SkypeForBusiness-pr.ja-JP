---
title: Microsoft Teams で Bookings アプリを管理する
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
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
- m365-frontline
- tier2
- highpri
- m365initiative-meetings
ms.reviewer: ''
description: 組織内のユーザーの Teams で Bookings アプリを管理する方法について説明します。
ms.openlocfilehash: abcd906f18b10b7d82b67682de439f1eb6592cd6
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307522"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Microsoft Teams で Bookings アプリを管理する

Microsoft Teams の Bookings アプリでは、対人予約と仮想予定を簡単にスケジュールできます。 たとえば、医療訪問、財務相談、面接、カスタマー サポート、教育オフィス時間などです。 詳細については、「[Teams と Bookings アプリを使用した仮想予定](/microsoft-365/frontline/bookings-virtual-appointments)」を参照してください。

スケジューラは、1 つのエクスペリエンスから、複数の部署とスタッフの予定表と、内部および外部の出席者との通信を管理できます。 仮想予定は、堅牢なビデオ会議機能を提供する Teams 会議を介して開催されます。

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Teams で Bookings アプリを使用するための前提条件

* Exchange メールボックスがExchange Online。 オンプレミスExchange Serverメールボックスはサポートされていません。
* Microsoft Bookingsは組織で使用できます。
* ユーザーは適切なライセンスを持っています。 Office 365 A3、A5、E1、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3、Business Standard がサポートされています。
* Bookings アプリのすべてのユーザーと会議に参加するすべてのスタッフは、Teams 会議のスケジュール設定をサポートするライセンスを持っています。
* [ソフトウェアとブラウザーの前提条件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams での Bookings の利用可能性

Teams の Bookings アプリは、デスクトップと Web で利用できます。 [ [Teams のアプリ] と [Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 管理センターの **アプリの管理** ] の下にあります。

## <a name="control-access-to-bookings-within-your-organization"></a>組織内の Bookings へのアクセスを制御する

Bookings アプリにアクセスできるユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。 Microsoft Bookingsアプリを使用できるようにするか、Microsoft 365 管理センターから無効にすることができます。 または、Bookings アプリ ポリシーを作成して、選択したユーザーが Bookings カレンダーを作成できるようにします。 「[Microsoft Bookingsへのアクセスを取得する」を](/microsoft-365/bookings/get-access)参照してください。

Teams [アプリセットアップ ポリシーを作成して、選択したユーザー用に Bookings アプリをピン留め](teams-app-setup-policies.md)することもできます。

## <a name="recommended-meeting-policy-settings"></a>推奨される会議ポリシー設定

Bookings に最適なエクスペリエンスを実現するには、Teams 会議ポリシーを作成して、 **組織内のすべてのユーザー** を自動的に許可し、そのポリシーをスタッフに割り当てます。 このポリシーでは、スタッフが予定に自動的に参加し、外部出席者のロビー エクスペリエンスを有効にすることができます。 [会議にユーザーを自動的に許可する方法を](meeting-policies-participants-and-guests.md#automatically-admit-people)参照してください。

会議ポリシーの詳細については、「 [Teams での会議ポリシーの管理](meeting-policies-in-teams.md) 」および「Teams での [会議ポリシーと会議の有効期限](meeting-expiration.md)」を参照してください。

## <a name="sms-text-notifications"></a>SMS テキスト通知

![情報アイコン](media/info.png) **この機能は [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (プレビュー) に移行しています。ユーザーはプレビュー期間中も引き続きこの機能を使用できます。プレビュー後、ユーザーには Teams Premium ライセンスが必要です。**

組織内のスタッフによってスケジュールされた仮想予定について、SMS テキスト通知を外部出席者に送信できるかどうかを制御できます。

既定では、この設定はオンになっており、組織内のすべての Bookings カレンダーに対して SMS テキスト通知が有効になっています。 Bookings 管理者とスケジューラは、スケジュール [された予定の種類とスケジュール](/microsoft-365/frontline/bookings-virtual-appointments#scheduled-appointment-type) された個々の予定で、必要に応じて SMS 通知をオフまたはオンにすることを後で選択できることに注意してください。

この設定を構成するには、Microsoft 365 管理センター \> **設定** \> **組織の設定** に移動し、[**Bookings**]\(予約\) を選択します。 [**Microsoftによる SMS テキスト メッセージ通知の送信を許可する**] チェック ボックスをオンまたはオフにします。

[組織の SMS テキスト通知を構成する](/microsoft-365/bookings/turn-bookings-on-or-off)方法について詳しくは、こちらをご覧ください。

## <a name="optional-staff-approvals-setting"></a>オプションのスタッフ承認設定

Bookings がスケジュールの空き時間情報を共有する前に、また他のユーザーが予約をスケジュールする前に、スタッフにオプトインを要求できます。

この設定を有効にするには、Microsoft 365 管理センター \> **設定** \> **組織の設定** に移動し、[**Bookings**]\(予約\) を選択します。 [ **スタッフの承認を要求する** ] チェック ボックスをオンにします。

この設定をオンにすると、スタッフは予約カレンダーへのメンバーシップの承認を求めるメールを受け取ります。  

[スタッフの承認設定を構成する方法](/microsoft-365/bookings/turn-bookings-on-or-off)の詳細については、こちらをご覧ください。

## <a name="changing-your-default-domain-when-setting-up-a-bookings-mailbox"></a>Bookings メールボックスを設定するときに既定のドメインを変更する

Bookings メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメール ドメインが使用されます。 ただし、既定のドメインでは、外部の受信者に会議出席依頼を送信するときに問題が発生する可能性があります。 たとえば、招待が迷惑メールとしてフラグが設定され、受信者の迷惑メール フォルダーに移動され、受信者に招待が表示されない場合があります。

Bookings メールボックスを作成する前に、既定のドメインを変更することをお勧めします。 [「ドメインに関する FAQ」を](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365)参照してください。

Bookings メールボックスの作成後に既定のドメインを変更する必要がある場合は、PowerShell を使用します。

```powerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

詳細については、「メールボックスの [設定](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。

> [!NOTE]
> Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange とExchange Online間のメール フローを徹底的にテストすることをお勧めします。

## <a name="send-feedback"></a>フィードバックを送信する

以下に関するフィードバックをお寄せください。

* ユーザー エクスペリエンスまたは使いやすさ
* 機能のギャップまたは不足している機能
* バグや問題
  
フィードバックを送信するには、Teams の左側のナビゲーション バーの下部にある **[ヘルプ**] オプションを選択し、[**すべての****問題に関する問題の報告**] を選択します。 フィードバック レポートの冒頭で、Bookings の問題を簡単に特定できるように、"Bookings" に関するフィードバックを送信していることを示します。

## <a name="related-articles"></a>関連記事

[ブラウザーでの Teams 仮想予定の参加エクスペリエンスを管理する](/microsoft-365/frontline/browser-join)


  [エンド ユーザー向け Bookings ドキュメント](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
