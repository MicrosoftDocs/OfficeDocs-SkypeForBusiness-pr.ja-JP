---
title: Microsoft Teams の概要
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.date: 11/06/18
ms.reviewer: LolaJ
description: Microsoft Teams とそのインフラストラクチャについて、および Office 365 と組み合わせた Teams の使用について説明します。
localization_priority: Priority
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02848be0401bf06fff989b9b5ab79cdddcc70070
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240678"
---
# <a name="welcome-to-microsoft-teams"></a>Microsoft Team にようこそ

所属する組織での Microsoft Teams の管理者である場合は、このページの内容をよくお読みください。 Teams を計画、展開、実行するために必要なすべての情報を得ることができます。  

## <a name="overview-of-teams"></a>Teams の概要

Teams を初めて使用する場合は、短いビデオ「[Welcome to Teams (Teams へようこそ)](https://support.office.com/article/video-welcome-to-microsoft-teams-b98d533f-118e-4bae-bf44-3df2470c2b12?wt.mc_id=otc_microsoft_teams)」をご覧ください。 Teams は Office 365 グループ、Office Graph、および他の Office 365 と同じエンタープライズ レベルのセキュリティ、コンプライアンス、管理容易性で構築されています。 Teams は Azure Active Directory (Azure AD) に保存された ID を活用します。 チームを作成すると、次のものが作成されることになります。
- 新しい [Office 365 グループ](office-365-groups.md)
- チームのファイルを保存するための [SharePoint Online](sharepoint-onedrive-interact.md) サイトとドキュメント ライブラリ
- [Exchange Online](exchange-teams-interact.md) の共有メールボックスとカレンダー
- OneNote ノートブック
- Planner や Power BI などのその他の Office 365 アプリとの連動

既存のグループからチームを作成する場合、グループのメンバーシップ、サイト、メールボックス、ノートブックは Teams に移行されます。 新しい[組織全体のチーム](create-an-org-wide-team.md)について、必ず理解してください。これは、自分の組織内のあらゆるユーザーを引き入れて、ユーザーが組織に参加したり組織から脱退したりするたびに、Active Directory を使用してメンバーシップを最新の状態に維持する、特別な種類のチームです。 

Teams をカスタマイズしたり拡張したりするには、[タブ](built-in-custom-tabs.md)、[コネクタ](office-365-custom-connectors.md)、および[ボット](add-bots.md)を介してサードパーティ アプリを追加します。 Teams では、組織の外部のユーザーを、[ゲストとして追加すること](guest-access.md)によって、チームまたはチャネルに含めることができます。 Office 365 の一部として、Teams は強力な[拡張性](https://docs.microsoft.com/en-us/microsoftteams/platform)を提供しており、自分の組織に必要なチームワーク ハブを構築することができます。 

![Teams のデスクトップ アプリとモバイル アプリ](media/teams-overview-hub.png)

Teams は Office 365 でのインテリジェント コミュニケーションのプライマリ クライアントで、時の経過とともに Skype for Business Online に取って代わります。 Teams に導入された Skype for Business の機能の詳細については、「[Skype for Business から Microsoft Teams へ: 機能のロードマップ](http://aka.ms/skype2teamsroadmap)」をご覧ください。 常設チャットおよびメッセージの機能を補完するために、Teams では内蔵され完全に統合された音声とビデオによる、包括的な会議および通話のエクスペリエンスを提供しています。 Microsoft Teams ブログの「[Teams is now a complete meeting and calling solution (完全な会議および通話ソリューションとなった Teams)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)」をご覧ください。

## <a name="teams-admin-experience"></a>Teams の管理者エクスペリエンス

新しい Microsoft Teams と Skype for Business の管理センターを展開しています。 これをまだ確認していない場合でも、次第に展開が進行して、Teams と Skype for Business を管理するための統一されたエクスペリエンスを利用できるようになります。 2018 年 3 月から、Skype for Business 管理センターと、Office 365 管理センターでの Teams エクスペリエンスの両方の設定を順次、新しい管理センターに移行しています。 

移行中、2 つの異なる管理者エクスペリエンスに分離されます。 ユーザーが迷うことがないように構成してありますので、安心してください。 設定の移行後、通知が表示され、新しい Microsoft Teams および Skype for Business 管理センター内のその設定の新しい場所に導かれます。 詳細については、「[新しい Microsoft Teams および Skype for Business の管理センターへの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)」をご覧ください。 

Teams およびその他の Office 365 製品とサービスに今後導入される機能についての最新情報を常に取得するには、必ず[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) と [Teams ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams)を確認してください。 新機能および更新された機能、計画済みの変更、および問題についての通知を取得して、常に情報を把握して準備を整えられるようになります。 

## <a name="upgrade-from-skype-for-business-to-teams"></a>Skype for Business から Teams へのアップグレード
既に Teams をご利用ですね。 ここのリソースを使用して、所属する組織のチームワークのための中央ハブとして Teams を最大限に有効活用します。 

Skype for Business を実行していて、Teams にアップグレードする準備が整っている場合、または Skype for Business と Teams を共存させて実行していて、完全に Teams に移動する準備が整っている場合、その移行作業を正常に完了させるために役に立つツール、ヒント、ガイダンスを利用することができます。 詳細については、「[Skype for Business から Microsoft Teams へのアップグレード](journey-skypeforbusiness-teams.md)」をご覧ください。

## <a name="teamwork-and-office-365"></a>チームワークと Office 365
すべてのチームはそれぞれ異なります。コラボレーションを行うための万能の手段はありません。 Office 365 は各チームの固有のニーズを満たすよう設計されていて、ユーザーが通信、共同作業などより多くのことを専用の統合アプリで成し遂げられる能力を強化します。 

どの Office 365 アプリおよびサービスを使用するかを決めるときに、自分の組織で行われる作業や、所属するチームで行う必要がある会話の種類について考えます。 

- **Teams** は、中核的なプロジェクトにおいて緊密に協力して作業を行うユーザーが、能動的にリアルタイムでつながってコラボレーションを行い作業を完了することができる、デジタル ハブです。 ドキュメントの共同作成や、会議の開催や、他のアプリやサービスでの共同作業など、作業が発生したその場で会話を交わします。 Teams は、くだけたチャットを行ったり、プロジェクトに対して速やかに反復作業を行ったり、チームのファイルで作業したり、共有された成果物でコラボレーションを行ったりするための場所となります。 

- **Outlook** は、使い慣れた電子メール環境や、より丁寧で真面目な方法でコラボレーションを行うために、またはターゲットを絞って直接コミュニケーションをとる場合に使用されます。 

- **SharePoint** は、サイト、ポータル、インテリジェント コンテンツ サービス、ビジネス プロセスの自動化、およびエンタープライズ検索で活用されます。 SharePoint はコンテンツをフレームワークの中心で保持して、あらゆる種類のコンテンツをチーム全体で簡単に共有可能およびアクセス可能にします。 Outlook、Yammer、および Teams との緊密な統合により、会話のクスぺリエンス全体にわたって、シームレスなコンテンツのコラボレーションを実現します。   

- **OneDrive for Business** は、ファイルを保管したり、招待した他のユーザーと共有するために利用できます。 ユーザーが OneDrive for Business に保存するコンテンツは、ユーザーが他の人と共有するまで、プライベートとなります。これは、共有するつもりがない、または共有するための準備が整っていない個人のドキュメントや下書きのドキュメントを保管するためには最良のオプションです。

- **Yammer** は、組織全体にわたるユーザーを接続するために使用します。 会社全体の取り組みを推進したり、ベスト プラクティスを共有したり、一般的な領域または関心のある話題や実践に関するコミュニティを構築したりすることができます。 クラウドソーシングのアイデアで、会社全体にわたるユーザーとのオープンなディスカッションを促進します。

- **Office アプリ**は、Word、Excel、 PowerPoint、OneNote などを含む、すべてユーザーが良く知っていて、恒常的に使用している、慣れ親しんだツールです。 

## <a name="teams-known-issues"></a>Teams の既知の問題

「[Microsoft Teams の既知の問題](Known-issues.md)」をご覧ください。

## <a name="teams-client-release-notes"></a>Teams クライアントのリリース ノート

「[Microsoft Teams の新機能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)」をご覧ください。

