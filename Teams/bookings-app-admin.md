---
title: Microsoft Teams でのアプリと仮想訪問の予約
author: mattpennathe3rd
ms.author: v-mapenn
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: 予約アプリを使用した Microsoft Teams と仮想アクセス
ms.openlocfilehash: b00a42ab7d0b590d706b8e3218f24d13b945b731
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280289"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a>Microsoft Teams でのアプリと仮想訪問の予約

Microsoft Teams の予約アプリでは、医療機関の訪問、財務相談、面接、カスタマサポート、教育機関の時間など、個人や仮想の予定をスケジュールするための簡単な方法が用意されています。

スケジューラは、1つのエクスペリエンスから複数の部門とスタッフの予定表を管理したり、内部および外部の出席者との通信を管理したりすることができます。 仮想の予定は Microsoft Teams の会議によって開催されます。これには、強力なビデオ会議機能が備わっています。

> [!NOTE]
> Teams で予約アプリをインストールする必要があるのは、スケジューラだけです。 仮想予定を開催または参加しているスタッフには、アプリは必要ありません。 自分の Outlook または Teams の予定表から、または予約確認メールのリンクから、予定を簡単に追加することができます。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Teams で予約アプリを使用するための前提条件

- Exchange メールボックスは Exchange Online にある必要があります。 オンプレミスの Exchange Server メールボックスはサポートされません。

- 組織で Microsoft 予約を有効にする必要があります。

- ユーザーは適切なライセンスを持っている必要があります。 Office 365 A3、A5、E3、E5、および Microsoft 365 Business Standard、A3、A5、E3、E5 がサポートされています。

- 予約アプリのすべてのユーザーと会議に参加しているすべてのスタッフは、チーム会議のスケジュールをサポートするライセンスを持っている必要があります。

- システムは、[ソフトウェアとブラウザーのすべての前提条件を](hardware-requirements-for-the-teams-app.md)満たしている必要があります。

## <a name="availability-of-bookings-in-teams"></a>Teams での予約の利用

Teams 用 Microsoft 予約アプリは、デスクトップと web で利用できます。 [ [Microsoft teams 内のアプリ](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)] および [Teams 管理センター内の**アプリを管理**する] の下にあります。

### <a name="control-access-to-bookings-within-your-organization"></a>組織内の予約へのアクセスを制御する

予約アプリへのアクセス権を持つユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。 Microsoft 365 管理センターで Microsoft の予約を有効または無効にする方法、および選択したユーザーが予約予定表を作成できるようにするための予約アプリポリシーを作成する方法については、「 [Microsoft 予約へのアクセスを取得](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)する」を参照してください。 また、[選択したユーザーのために予約アプリをピン留めする Teams アプリポリシーを作成](teams-app-setup-policies.md)する方法についても説明します。

## <a name="recommended-meeting-policy-settings"></a>推奨される会議のポリシー設定

予約に最適なエクスペリエンスを実現するには、スタッフ会議ポリシーを作成し**て、組織内の全員**に自動的に参加するようにします。 これにより、スタッフは予定に自動的に参加できるようになり、外部の出席者に対してロビーエクスペリエンスを有効にすることができます。 [会議へのユーザーの自動 admitting](meeting-policies-in-teams.md#automatically-admit-people)の詳細については、こちらを参照してください。

### <a name="optional-staff-approvals-setting"></a>省略可能なスタッフ承認設定

追加のプライバシー設定として、[空き時間情報のスケジュールを設定する] をオンにしておくことを選択できます。そのためには、予約で予約されていない場合は、予約で予約することができます。  

この設定を有効にするには、 **Microsoft 365 管理センター**の設定に移動して \> **Settings** \> **Settings**、[**予約**] を選択します。

この設定を有効にすると、スタッフは、予約予定表へのメンバーシップを承認するように求められるメールを受信します。  

この機能は、世界中の Microsoft 365 および Office 365 のユーザーに段階的に展開されています。 すべてのオプションが現在の環境で利用できない場合は、しばらくお待ちください。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>予約メールボックスの設定時に既定のドメインを変更する

予約メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメールドメインが使用されます。 ただし、外部の受信者に会議の出席依頼を送信するときに問題が発生する可能性があります。招待状はスパムとしてマークされ、受信者の [迷惑メール] フォルダーに移動されることがあります。そのため、受信者には招待が表示されない可能性があります。

予約メールボックスを作成する前に、既定のドメインを変更することをお勧めします。 この方法については、「ドメインに関する[FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)」を参照してください。

予約メールボックスが既に作成された後で既定のドメインを変更する必要がある場合は、PowerShell で次の操作を行うことができます。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

詳細については、「 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) 」コマンドレットの PowerShell ドキュメントを参照してください。

> [!NOTE]
> Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange と Exchange Online の間のメールフローを徹底的にテストすることをお勧めします。

## <a name="sending-feedback"></a>フィードバックの送信

お客様からのフィードバックを歓迎します。

  - ユーザーエクスペリエンスまたは使いやすさ
  - 機能のギャップまたは不足している機能
  - バグまたは問題
  
フィードバックを送信するには、Teams の左側のナビゲーションバーの下部にある [**ヘルプ**] ボタンをクリックし、[問題の**報告** **] をクリック**します。 予約の問題を簡単に特定できるように、フィードバックレポートの最初に、"予約" についてのフィードバックを送信していることを確認してください。

## <a name="related-topics"></a>関連項目

[エンドユーザー向けの予約ドキュメント](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
