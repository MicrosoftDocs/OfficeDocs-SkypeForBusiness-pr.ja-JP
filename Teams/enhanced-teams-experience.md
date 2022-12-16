---
title: Microsoft Teams Premium - 管理者向けの概要
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: ''
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
description: 管理者と IT プロフェッショナル向けの Teams Premium Microsoftについて説明します。
ms.openlocfilehash: 9e7af9c777ba5fec8ca8b68da7f1069737702617
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392477"
---
# <a name="microsoft-teams-premium---overview-for-administrators"></a>Microsoft Teams Premium - 管理者向けの概要

![情報アイコン](media/info.png) **この記事で説明するほとんどの機能には、プレビュー リリースである Teams Premium が必要です。** 一部のウェビナー機能など、いくつかの機能は、他のライセンスでも利用できます。 機能の可用性とライセンスの詳細については、「 [Teams Premium ライセンス](teams-add-on-licensing/licensing-enhance-teams.md)」を参照してください。

この記事は、Teams Premium 機能を展開および構成する IT 担当者と管理者向けです。 この記事では、機能の簡単な説明と、より詳細なドキュメントへのリンクを示します。

Teams Premium は、Teams に次の機能強化を提供するアドオン ライセンスです。  

-   エンド ユーザー向けの会議エクスペリエンスの強化
-   会議のセキュリティと保護の強化 
-   管理とテレメトリのサポートの強化


> [!IMPORTANT]
> Teams Premium はパブリック プレビュー リリースであるため、一般公開時に Teams で現在利用できる一部の機能は、Teams Premium ライセンスでのみ使用できます。 

次のセクションでは、次の Teams Premium の機能強化について説明します。

- [保護された会議](#protected-meetings)
- [カスタム会議](#custom-meetings)
- [Premium イベント](#premium-events)
- [仮想予定](#advanced-virtual-appointments)

> [!Note]
>この記事は引き続き更新されます。 新しいコンテンツへのリンクを頻繁に確認してください。

## <a name="protected-meetings"></a>保護された会議

Teams Premium には、次の重要な機能を使用して会議を保護するための追加の方法が用意されています。 

- **秘密度ラベル** - 会議開催者によって通常制御される会議設定を制御するための秘密度ラベルの拡張機能。 これらの機能には、ロビー、チャット、チャットコピー、プレゼンテーション、録音機能を制御するための新しい設定が含まれます。

- **透かし** - 秘密度ラベルを使用して適用されます。 透かしには会議参加者のメール アドレスが表示されます。これは、会議で共有されている機密情報を保護するのに役立ちます。 

- **エンドツーエンドの暗号化** - 秘密度ラベルを介して適用されます。 エンドツーエンドの暗号化により、より高いレベルの保護が必要な会議のセキュリティが強化されます。


| 機能/タスク  | 管理者向けのドキュメント | エンド ユーザー向けのドキュメント
| -------------------- | ----------- | ------------ |
| 秘密度ラベル | [3 層の保護を使用して Teams 会議を構成する](configure-meetings-three-tiers-protection.md) | |
| 透かし | [会議に透かしを要求する](watermark-meeting-content-video.md) | [会議の透かし](https://support.microsoft.com/office/watermark-for-teams-meetings-a9166432-f429-4a19-9a72-c9e8fdf4f589)|
| エンドツーエンド暗号化 (E2EE) | [機密性の高い会議の暗号化](end-to-end-encrypted-meetings.md) | [暗号化を使用する](https://support.microsoft.com/office/use-end-to-end-encryption-for-teams-meetings-a8326d15-d187-49c4-ac99-14c17dbd617c)  |
| テンプレート、ラベル、ポリシー | [テンプレート、秘密度ラベル、ポリシー](meeting-templates-sensitivity-labels-policies.md)  | [カスタム テンプレートを使用する](https://support.microsoft.com/office/use-custom-templates-for-teams-meetings-78279be9-3283-4999-b24e-96fb0da2fb4f) |
| 記録できるユーザーを制限する | [機密性の高い会議の記録を管理する](manage-meeting-recording-options.md) | [会議のレコーディング](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24?storagetype=stage#bkmk_whocanstartorstoparecording) |


## <a name="custom-meetings"></a>カスタム会議

Teams Premium には、会議をカスタマイズするための次の追加機能が用意されています。

- **会議テンプレート - 会議** の開催者が通常制御する会議設定を制御するために使用されます。 テンプレートを使用すると、組織内で一貫した会議エクスペリエンスを作成し、コンプライアンス要件とビジネス ルールを適用できます。

- **会議のテーマ** - 組織が会議エクスペリエンス全体でビジュアル ID を拡張できるようにします。 1 つのテナント内で、さまざまな部署や部署の会議テーマを設定および作成できます。

- **組織のカスタム会議の背景** - カスタム会議の背景を作成して定義し、その後、Teams Premium ライセンスを使用してエンド ユーザーが使用できるようにします。

- **組織向けのカスタム 一緒モード シーン** - Teams Premium ライセンスを使用してエンド ユーザーが使用できる会議のカスタム 一緒モード シーンを作成、カスタマイズ、または受け入れます。


| 機能/タスク | 管理者向けのドキュメント | エンド ユーザー向けのドキュメント
| -------------------- | ----------- | ------------ |
| 会議テンプレート | - [概要](custom-meeting-templates-overview.md)<br>- [カスタム会議テンプレートを作成する](create-custom-meeting-template.md)| [カスタム テンプレートを使用する](https://support.microsoft.com/office/use-custom-templates-for-teams-meetings-78279be9-3283-4999-b24e-96fb0da2fb4f)
| 会議のテーマ | [Teams 会議のテーマ](meeting-themes.md) | [会議のテーマを使用する](https://support.microsoft.com/office/use-meeting-themes-for-teams-meetings-fbfd826d-1112-4790-918a-5a82cac8250e) |
| 組織のカスタム会議の背景 | [会議の背景](custom-meeting-backgrounds.md)| |
| 組織向けのカスタム 一緒モード シーン | [ユーザーと開発者向けのコンテンツ](/microsoftteams/platform/apps-in-teams-meetings/teams-together-mode)| |





## <a name="premium-events"></a>Premium イベント

Teams Premium では、新しい Teams イベント ポリシーを使用してユーザーに高度なウェビナー エクスペリエンスを提供します。 登録と追跡を引き続きサポートする一方で、新しいポリシーでは、会議の開催者や開催者に次のような機能も提供されます。

- **使用条件のカスタム質問** - 出席者に提示する。
- **発表者のバイオ - 発表者** に関する情報を含めます。
- **バナー、ロゴ、定義済みの色** - カスタマイズされたビジュアル ウェビナー エクスペリエンスを提供します。
- **高度な登録機能** - 手動承認、待機リスト、登録日時制限を含む。
- **登録の概要と管理** - イベントごとに、有効になっている登録機能に応じて、登録状態が異なる出席者のリストを含む登録状態の概要。


| 機能/タスク | 管理者向けのドキュメント | エンド ユーザー向けのドキュメント
| -------------------- | ----------- | ----------- |
| 会議、ウェビナー、ライブ イベントについて理解する | [クイック スタート](quick-start-meetings-live-events.md) | |
| ウェビナーを設定する | [ウェビナーを設定する](set-up-webinars.md) | - [ウェビナーの登録を管理する](https://support.microsoft.com/office/manage-webinar-registration-923f382a-0cca-433a-b38d-7461971192d1) <br> - [出席者に表示される内容を管理する](https://support.microsoft.com/office/manage-what-attendees-see-in-teams-meetings-19bfd690-8122-49f4-bc04-c2c5f69b4e16)|
| ウェビナーの会議ポリシー | [会議ポリシー](meeting-policies-in-teams-general.md) | |




## <a name="advanced-virtual-appointments"></a>高度な仮想予定

Microsoft 365 ライセンスを使用すると、エンド ユーザーは基本的な仮想予定機能を使用して、ビジネス間の会議をスケジュールして参加できます。 たとえば、ユーザーは Bookings 予定表で予定をスケジュールでき、外部の出席者は Teams をダウンロードしなくてもブラウザーを介して参加できます。 

Teams Premium には、次のような高度な仮想予定機能が用意されています。

- SMS 通知
- カスタム待合室
- スケジュールされた予定とオンデマンドの予定のキュー
- 分析

| 機能/タスク  | 管理者向けのドキュメント | 
| -------------------- | ----------- | 
| SMS 通知  | [SMS テキスト通知](bookings-app-admin.md#sms-text-notifications) | 
| レポート | [仮想予定使用状況レポート](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)<br>[詳細な仮想予定 アクティビティ レポート](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) | 



## <a name="additional-resources"></a>その他のリソース

その他のリソースについては、こちらを参照してください。

- [Teams Premium 製品サイトのMicrosoft](https://www.microsoft.com/microsoft-teams/premium)
- [Microsoft Teams Premium ブログ](https://www.microsoft.com/microsoft-365/blog/2022/10/12/introducing-microsoft-teams-premium-the-better-way-to-meet/)


