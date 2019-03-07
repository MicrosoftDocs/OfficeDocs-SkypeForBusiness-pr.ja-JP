---
title: Microsoft Team にようこそ
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.date: 01/28/2019
ms.reviewer: LolaJ
description: Microsoft Teams を組織に展開するための正しい経路を見つけます。 Teams のインフラストラクチャと、Office 365 での Teams の使用について説明します。
localization_priority: Priority
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ee4cba00f20eb53630845f1956d88d47e333084
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458869"
---
# <a name="welcome-to-microsoft-teams"></a>Microsoft Team にようこそ
所属する組織での Microsoft Teams の管理者である場合は、このページの内容をよくお読みください。 Teams を使用する準備が整っている場合は、「[Teams の展開方法](How-to-roll-out-teams.md)」から始めてください。

Teams について不慣れな場合や、詳細が必要な場合は、このまま読み進めてください。

## <a name="overview-of-teams"></a>Teams の概要

Teams を初めて使用する場合は、短いビデオ「[Teams の紹介](https://youtu.be/s3aQV3T0D6c)」を参照してください。 Teams は Office 365 グループ、Office Graph、および他の Office 365 と同じエンタープライズ レベルのセキュリティ、コンプライアンス、管理容易性で構築されています。 Teams は Azure Active Directory (Azure AD) に保存された ID を活用します。 チームを作成すると、次のものが作成されることになります。
- 新しい [Office 365 グループ](office-365-groups.md)
- チームのファイルを保存するための [SharePoint Online](sharepoint-onedrive-interact.md) サイトとドキュメント ライブラリ
- [Exchange Online](exchange-teams-interact.md) の共有メールボックスとカレンダー
- OneNote ノートブック
- Planner や Power BI などのその他の Office 365 アプリとの連動

既存のグループからチームを作成する場合は、グループのメンバーシップ、サイト、メールボックス、ノートブックが Teams に表示されます。 新しい[組織全体のチーム](create-an-org-wide-team.md)について、必ず理解してください。これは、自分の組織内のあらゆるユーザーを引き入れて、ユーザーが組織に参加したり組織から脱退したりするたびに、Active Directory を使用してメンバーシップを最新の状態に維持する、特別な種類のチームです。 

Teams をカスタマイズおよび拡張するには、[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を使用してサードパーティ アプリを追加します。 Teams では、組織の外部のユーザーを[ゲストとして追加する](guest-access.md)ことで、チームまたはチャネルに含めることができます。 Office 365 の一部として、Teams は強力な[開発プラットフォーム](https://docs.microsoft.com/en-us/microsoftteams/platform)を提供します。これにより、ユーザーは組織に必要なチームワーク ハブを構築できます。 

![Teams のデスクトップ アプリとモバイル アプリ](media/teams-overview-hub.png)


## <a name="managing-teams"></a>Teams を管理する

ユーザーは管理者として、Microsoft Teams 管理センター経由で Teams を管理します。 詳細情報
- [Microsoft Teams 管理センターで Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)
- [新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](manage-teams-in-modern-portal.md)


Teams およびその他の Office 365 製品とサービスに今後導入される機能についての最新情報を常に取得するには、必ず[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) と [Teams ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams)を確認してください。 新機能および更新された機能、計画済みの変更、および問題についての通知を取得して、常に情報を把握して準備を整えられるようになります。 

## <a name="upgrade-from-skype-for-business-to-teams"></a>Skype for Business から Teams へのアップグレード
Teams は Office 365 でのインテリジェント コミュニケーションのプライマリ クライアントで、最終的に Skype for Business Online に取って代わるものとなります。 Teams に導入される新機能の詳細については、「[Microsoft 365 ロードマップ](http://aka.ms/O365Roadmap)」を参照してください。 常設チャットおよびメッセージの機能を補完するために、Teams では内蔵され完全に統合された音声とビデオによる、包括的な会議および通話のエクスペリエンスを提供しています。 Microsoft Teams ブログの「[Teams is now a complete meeting and calling solution (完全な会議および通話ソリューションとなった Teams)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)」をご覧ください。

Skype for Business を実行していて、Teams にアップグレードする準備が整っている場合、または Skype for Business と Teams を共存させて実行していて、完全に Teams に移動する準備が整っている場合、その移行作業を正常に完了させるために役に立つツール、ヒント、ガイダンスを利用することができます。 詳細については、「[Teams へのアップグレード](journey-skypeforbusiness-teams.md)」を参照してください。

## <a name="teamwork-and-office-365"></a>チームワークと Office 365
すべてのチームはそれぞれ異なります。コラボレーションを行うための万能の手段はありません。 Office 365 は各チームの固有のニーズを満たすよう設計されていて、ユーザーが通信、共同作業などより多くのことを専用の統合アプリで成し遂げられる能力を強化します。 

どの Office 365 アプリおよびサービスを使用するかを決めるときに、自分の組織で行われる作業や、所属するチームで行う必要がある会話の種類について考えます。 

- **Teams** は、チームワークのハブとして、組織内外のユーザーが積極的にリアルタイムでつながり、共同作業を完了できる場所です。 ドキュメントの共同作成や、会議の開催や、他のアプリやサービスでの共同作業など、作業が発生したその場で会話を交わします。 Teams は、くだけたチャットを行ったり、プロジェクトに対して速やかに反復作業を行ったり、チームのファイルで作業したり、共有された成果物でコラボレーションを行ったりするための場所となります。 

- **Outlook** は、使い慣れた電子メール環境や、より丁寧で真面目な方法でコラボレーションを行うために、またはターゲットを絞って直接コミュニケーションをとる場合に使用されます。 

- **SharePoint** は、サイト、ポータル、インテリジェント コンテンツ サービス、ビジネス プロセスの自動化、およびエンタープライズ検索で活用されます。 SharePoint はコンテンツをフレームワークの中心で保持して、あらゆる種類のコンテンツをチーム全体で簡単に共有可能およびアクセス可能にします。 Outlook、Yammer、および Teams との緊密な統合により、会話のクスぺリエンス全体にわたって、シームレスなコンテンツのコラボレーションを実現します。

- **OneDrive for Business** は、ファイルを保管したり、招待した他のユーザーと共有するために利用できます。 ユーザーが OneDrive for Business に保存するコンテンツは、ユーザーが他の人と共有するまで、プライベートとなります。これは、共有するつもりがない、または共有するための準備が整っていない個人のドキュメントや下書きのドキュメントを保管するためには最良のオプションです。

- **Yammer** は、組織全体にわたるユーザーを接続するために使用します。 会社全体の取り組みを推進したり、ベスト プラクティスを共有したり、一般的な領域または関心のある話題や実践に関するコミュニティを構築したりすることができます。 クラウドソーシングのアイデアで、会社全体にわたるユーザーとのオープンなディスカッションを促進します。

- **Office アプリ**は、Word、Excel、 PowerPoint、OneNote などを含む、すべてユーザーが良く知っていて、恒常的に使用している、慣れ親しんだツールです。 

## <a name="teams-known-issues"></a>Teams の既知の問題

「[Microsoft Teams の既知の問題](Known-issues.md)」をご覧ください。

## <a name="teams-client-release-notes"></a>Teams クライアントのリリース ノート

「[Microsoft Teams の新機能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)」をご覧ください。

