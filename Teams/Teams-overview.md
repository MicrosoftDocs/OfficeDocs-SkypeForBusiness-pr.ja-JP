---
title: Microsoft Teams にようこそ
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: LolaJ
description: Microsoft Teams を組織に展開するための正しい経路を見つけます。 Teams のインフラストラクチャと、Microsoft 365 または Office 365 での Teams の使用について説明します。
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.allteamsdocuments
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7220a7776acb796a4ca56ef28541fd821c0c0132
ms.sourcegitcommit: 18838ed1da69ab4668c903bfcafd4ad2fa02639d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773312"
---
# <a name="welcome-to-microsoft-teams"></a>Microsoft Teams にようこそ
所属する組織での Microsoft Teams の管理者である場合は、このページの内容をよくお読みください。 Teams を使用する準備が整っている場合は、「[Teams の展開方法](How-to-roll-out-teams.md)」から始めてください。

Teams を使うのが初めてで、詳細を知りたい場合は、「[Teams へようこそ](https://www.youtube.com/embed/s3aQV3T0D6c)」のビデオ (55 秒) をご覧ください。

Teams の管理者向けビデオの「Teams へようこそ」をお見逃しなく (3 分強):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE47cdp]

エンド ユーザー向けの Teams のヘルプを探している場合は、アプリの左側にある **[ヘルプ]** をクリックするか、[Microsoft Teams ヘルプ センター](https://support.office.com/teams)に移動します。 トレーニングについては、「[Microsoft Teams のトレーニング](training-microsoft-teams-landing-page.md)」を参照してください。 

## <a name="teams-architecture"></a>Teams のアーキテクチャ

Teams は Microsoft 365 グループ、Microsoft Graph、および他の Microsoft 365 および Office 365 と同じエンタープライズ レベルのセキュリティ、コンプライアンス、管理容易性で構築されています。 Teams は Azure Active Directory (Azure AD) に保存された ID を活用します。 Teams は、オフラインの場合やネットワークの状態が不安定な場合でも作業を続けます。

Microsoft 365 全体の中での Teams の位置を確認するには、次のアーキテクチャ ポスターを参照してください: [Microsoft 365 の一部としての Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

チームを作成すると、次のものが作成されることになります。
- 新しい [Microsoft 365 グループ](office-365-groups.md)
- チームのファイルを保存するための [SharePoint Online](sharepoint-onedrive-interact.md) サイトとドキュメント ライブラリ
- [Exchange Online](exchange-teams-interact.md) の共有メールボックスとカレンダー
- OneNote ノートブック
- Planner や Power BI などのその他の Microsoft 365 および Office 365 アプリとの連動

既存のグループからチームを作成する場合は、グループのメンバーシップ、サイト、メールボックス、ノートブックが Teams に表示されます。 詳細については、こちらのポスターをご覧ください: [ITアーキテクト向けMicrosoft 365のグループ](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

Teams をカスタマイズおよび拡張するには、[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を使用してサードパーティ アプリを追加します。 Teams では、組織の外部のユーザーを[ゲストとして追加する](guest-access.md)ことで、チームまたはチャネルに含めることができます。 Microsoft 365 および Office 365 の一部として、Teams は強力な[開発プラットフォーム](https://docs.microsoft.com/microsoftteams/platform)を提供します。これにより、ユーザーは組織に必要なチームワーク ハブを構築できます。 

> [!TIP]
> Teams のアーキテクチャの詳細については、[Teams Platform Academy (Teams プラットフォーム アカデミー)](https://aka.ms/TeamsPlatformAcademy) にある動画を視聴してください。


## <a name="managing-teams"></a>Teams を管理する

ユーザーは管理者として、Microsoft Teams 管理センター経由で Teams を管理します。 「Teams 管理センターを使用して Teams を管理する」のビデオ (3:03 分) で、簡潔なオリエンテーションをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

詳細情報:

- [Teams 管理者ロールを使用してTeams を管理します](using-admin-roles.md)
- [Teams 管理センターで Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)
- [新しい Teams 管理センターへの移行中に Teams を管理する](manage-teams-in-modern-portal.md)
- [Microsoft 365 または Office 365 の Teams 機能を管理する](enable-features-office-365.md)

Teams およびその他の Microsoft 365 および Office 365 製品とサービスに今後導入される機能についての最新情報を常に取得するには、必ず「[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)」と「[Teams ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)」を確認してください。 新機能および更新された機能、計画済みの変更、および問題についての通知を取得して、常に情報を把握して準備を整えられるようになります。 

## <a name="upgrade-from-skype-for-business-to-teams"></a>Skype for Business から Teams へのアップグレード
Teams は Microsoft 365 および Office 365 でのインテリジェント コミュニケーションの中心的なクライアントで、最終的に Skype for Business Online に取って代わります。 Teams に導入される新機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://aka.ms/O365Roadmap)」を参照してください。 常設チャットおよびメッセージの機能を補完するために、Teams では内蔵され完全に統合された音声とビデオによる、包括的な会議および通話のエクスペリエンスを提供しています。 Microsoft Teams ブログの「[完全な会議および通話ソリューションとなった Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)」をご覧ください。

Skype for Business を実行していて、Teams にアップグレードする準備が整っている場合、または Skype for Business と Teams を共存させて実行していて、完全に Teams に移動する準備が整っている場合、その移行作業を正常に完了させるために役に立つツール、ヒント、ガイダンスを利用することができます。 詳細については、「[Teams へのアップグレード](upgrade-start-here.md)」を参照してください。

## <a name="teamwork"></a>チームワーク
すべてのチームはそれぞれ異なります。コラボレーションを行うための万能の手段はありません。 Microsoft 365 および Office 365 は各チームの固有のニーズを満たすよう設計されていて、ユーザーが通信、共同作業などより多くのことを専用の統合アプリで成し遂げられる能力を強化します。

どの Microsoft 365 または Office 365 アプリおよびサービスを使用するかを決めるときに、自分の組織で行われる作業や、所属するチームで行う必要がある会話の種類について考えます。 

- **Teams** は、チームワークのハブとして、組織内外のユーザーが積極的にリアルタイムでつながり、共同作業を完了できる場所です。 ドキュメントの共同作成や、会議の開催や、他のアプリやサービスでの共同作業など、作業が発生したその場で会話を交わします。 Teams は、くだけたチャットを行ったり、プロジェクトに対して速やかに反復作業を行ったり、チームのファイルで作業したり、共有された成果物でコラボレーションを行ったりするための場所となります。 

- **Outlook** は、使い慣れた電子メール環境や、より丁寧で真面目な方法でコラボレーションを行うために、またはターゲットを絞って直接コミュニケーションをとる場合に使用されます。

- **SharePoint** は、サイト、ポータル、インテリジェント コンテンツ サービス、ビジネス プロセスの自動化、およびエンタープライズ検索で活用されます。 SharePoint はコンテンツをフレームワークの中心で保持して、あらゆる種類のコンテンツをチーム全体で簡単に共有可能およびアクセス可能にします。 Outlook、Yammer、および Teams との緊密な統合により、会話のクスぺリエンス全体にわたって、シームレスなコンテンツのコラボレーションを実現します。

- **OneDrive for Business** は、ファイルを保管したり、招待した他のユーザーと共有するために利用できます。 ユーザーが OneDrive for Business に保存するコンテンツは、ユーザーが他の人と共有するまで、プライベートとなります。これは、共有するつもりがない、または共有するための準備が整っていない個人のドキュメントや下書きのドキュメントを保管するためには最良のオプションです。

- **Yammer** は、組織全体にわたるユーザーを接続するために使用します。 会社全体の取り組みを推進したり、ベスト プラクティスを共有したり、一般的な領域または関心のある話題や実践に関するコミュニティを構築したりすることができます。 クラウドソーシングのアイデアで、会社全体にわたるユーザーとのオープンなディスカッションを促進します。

- **Office アプリ**は、Word、Excel、 PowerPoint、OneNote などを含む、すべてユーザーが良く知っていて、恒常的に使用している、慣れ親しんだツールです。 

## <a name="teams-content-updates"></a>Teams のコンテンツ アップデート

「[更新された Teams のトピックの週間リスト](teams-updates.md)」をご覧ください。

## <a name="teams-known-issues"></a>Teams の既知の問題

こちらを参照してください[Teams トラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)。

## <a name="teams-client-release-notes"></a>Teams クライアントのリリース ノート

「[ Teams の新機能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)」を参照してください。

