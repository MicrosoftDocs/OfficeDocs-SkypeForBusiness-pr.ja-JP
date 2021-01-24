---
title: Microsoft Teams でのミーティングと会議
ms.reviewer: ''
description: ここに示す展開のリソースを使用して、Microsoft Teams での会議と電話会議を展開します。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
- m365initiative-meetings
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 48ec728921f545f4e8c383b16a9bc4e82c22b363
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918683"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a>Microsoft Teams でのミーティングと会議

> [!NOTE]
> - リモート学習への移行の概要と開始に役立つリソースについては、「[**Remote Learning home page (リモート学習のホーム ページ)**](https://www.microsoft.com/education/remote-learning)」を参照してください。
> - 教職員や学生のリモート学習を支援するためのリソースは、「[**Office 365 Education のリモート教育と学習**](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4)」で利用することができます。


[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 この時点で、[電話会議](deploy-audio-conferencing-teams-landing-page.md)、ビデオ、および共有を含むミーティング ワークロードを追加する準備が整っています。 この記事では、会議と電話会議の展開について説明します。 まず、Teams 会議とデバイスのビデオを見ます (3:28 分):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

お客様のユーザーにおける会議エクスペリエンスの詳細については、「[会議と通話](https://support.office.com/article/meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)」をご覧ください。 


*2020 年 4 月の新機能*: 会議の開催者は、会議中に、会議のコントロールの **[会議を終了する]** をクリックすることで、Teams 内のすべての参加者に対して会議を終了できます。  

*2019 年 11 月の新機能*: [Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams を展開できる](use-advisor-teams-roll-out.md)ようになりました。 Teams のアドバイザー (プレビュー) を使用して、会議など、Teams の展開について説明します。 Office 365 環境を評価し、Teams で会議を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。

 > [!Note]
> 別のプラットフォームでの Teams のミーティングと会議についての詳細は、 [プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)を参照してください。

## <a name="meetings-and-conferencing-deployment-decisions"></a>ミーティングと会議の展開に関する決定事項

Teams は、すぐに使用できる優れたエクスペリエンスを組織に提供します。既定の設定は、ほとんどの組織の業務に通用します。 この記事では、自分の組織のプロファイルとビジネスの要件に基づいて既定の設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。 設定については 2 つのグループに分けて、まず、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分について説明します。 2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。

> [!Tip]
> ミーティングの詳細については、セッション「[Microsoft Teams でのミーティングの概要 (IT プロフェッショナル向け)](https://aka.ms/teams-meetings-intro)」を視聴してください。


## <a name="meetings-and-conferencing-prerequisites"></a>ミーティングと会議の前提条件

組織全体にミーティングの展開を広げる前に、できる限り最高のエクスペリエンスをユーザーに提供する環境が整っているかどうかを再確認するための時間を割いてください。 次の情報を確認して、環境に必要に応じた変更を実行します。

Teams の最高のエクスペリエンスを実現する場合、組織は Exchange Online および SharePoint Online を展開している必要があり、ユーザーには O365 の確認済みドメイン (*contoso.com* など) が必要になります。

組織全体にミーティングを組織全体に広げるには、すべてのユーザーの場所に Office 365 サービスへのインターネット アクセスが必要になります。 少なくとも、次に示す共通のポートがユーザーの場所からインターネットに対して開かれている必要があります。

- Teams で使用するクライアントからの送信 TCP 80 および 443
- Teams で使用するクライアントからの送信 UDP ポート 3478 から 3481

| 確認事項 | アクション |
|--------------|--------|
|Teams のミーティングの展開にネットワークが対応しているか? | ネットワークの対応状況を確認するには、次を参照してください。<ul><li>[Microsoft Teams 用に組織のネットワークを準備する](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</li><li>[URL と IP アドレスの範囲](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

次に示す設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では、組織に適した動作にならない場合)。

### <a name="teams-administrators"></a>Teams の管理者

Teams は、組織のチームを管理するために使用できる、カスタムの管理者ロールのセットを提供します。ロールは、管理者がさまざまな機能を使用できるようにします。 

| 確認事項 | アクション |
|--------------|--------|
|Teams 通信管理者の役割を誰に割り当てるか?|Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。|
|Teams 通信サポート エンジニアの役割を誰に割り当てるか?|管理者の役割を割り当てるには、「[Active Directory で管理者の役割と管理者以外の役割をユーザーに割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。|
|Teams 通信サポート スペシャリストの役割を誰に割り当てるか?||
|||

### <a name="meetings-settings"></a>ミーティングの設定 

ミーティングの設定は、匿名ユーザーが Teams のミーティングに参加できるようにするかどうかを制御する場合、ミーティングの出席依頼をセットアップする場合、およびサービスの品質 (QoS) をオンにするときにリアルタイム トラフィック用のポートを設定する場合に使用します。 これらの設定は、組織のユーザーがスケジュール設定するすべての Teams のミーティングに使用されます。 

| 確認事項 | アクション |
|--------------|--------|
|初期のミーティングの設定をカスタマイズするか? |ミーティングの設定の詳細については、[Teams のミーティングのチュートリアル](tutorial-meetings-in-teams.yml)を参照してください。|
|QoS を実装するか?|QoS の概念、シナリオ、および実装の詳細は、「[Microsoft Teams でのサービスの品質](qos-in-teams.md)」を参照してください 。|
|||

### <a name="meeting-policies"></a>ミーティング ポリシー

ミーティングのポリシーは、Teams のミーティングに参加するときにユーザーが使用できる機能を制御するために使用します。 既定のポリシーを使用することも、ミーティングをホストする組織内のユーザーに応じた 1 つ以上のポリシーを作成することもできます。 詳細については、[Microsoft Team のミーティングのチュートリアル](tutorial-meetings-in-teams.yml)を参照してください。

| 確認事項 | アクション |
|--------------|--------|
|<ul><li>初期のミーティング ポリシーをカスタマイズするか?</li><li>複数のミーティング ポリシーが必要か?</li><li>どのユーザーのグループにどのミーティング ポリシーを適用するかについて判断する方法は?</li></ul>|<br>「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)」を参照してください。|
|||

### <a name="audio-conferencing"></a>電話会議

電話会議により、組織はあらゆる (臨時またはスケジュールされた) ミーティングへの追加のエントリ ポイントを得られます。会議の参加者は従来の固定電話回線、構内電話交換機 (PBX)、または携帯電話を使用して電話することで、公衆交換電話網 (PSTN) を通じてミーティングに参加できます。 

電話会議を展開する準備が整っている場合は、詳細な[電話会議の展開](deploy-audio-conferencing-teams-landing-page.md)ガイダンスを参照してください。

### <a name="meeting-room-and-personal-devices"></a>会議室と個人用デバイス

Teams のミーティング エクスペリエンスを最適なものにするために、Teams のデバイス (会議室システム、電話機、ヘッドセット、カメラなど) の使用について検討してください。 詳細については、[インテリジェントなコミュニケーションのための Teams のデバイス](https://products.office.com/microsoft-teams/across-devices)を参照してください。

| 確認事項 | アクション |
|--------------|--------|
|ユーザーのために個人用デバイスを購入するか? |「[Teams でのデバイスを管理する](devices/device-management.md)」を参照してください。 |
|会議室に会議室システムのデバイスを購入して配備するか?|「[会議室のデバイスとソリューション](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」を参照してください。|
|||

### <a name="reporting"></a>レポート

アクティビティ レポートを使用して、組織内のユーザーがどのように Teams を使用しているかを調べます。 たとえば、まだ Teams を使用していないユーザーがいる場合、そのユーザーは使用の開始方法を知らないか、Teams を使用して生産性と共同作業の効率を向上させる方法を理解していない可能性があります。 組織では、アクティビティ レポートを使用して、トレーニングとコミュニケーションに関する優先項目を判断できます。 


| 確認事項 | アクション |
|--------------|--------|
|レポート作成の担当者を誰にするか?|「[Teams のアクティビティ レポートを使用する](teams-activity-reports.md)」を参照してください。  |
|使用状況の監視の担当者を誰にするか?|「[Teams での使用状況とフィードバックを監視する](get-started-with-teams-monitor-usage-and-feedback.md)」を参照してください。|
|||

## <a name="additional-deployment-decisions"></a>その他の展開に関する決定事項

次の設定は、組織のニーズと構成に基づいて変更できます。

### <a name="bandwidth-planning"></a>帯域幅の計画 

帯域の計画により、組織は組織のワイド エリア ネットワークとインターネットのリンク全体でミーティングをサポートするために必要な帯域幅の推定が可能になり、ミーティング サービスの拡大をサポートするためにネットワークが適切にプロビジョニングされていることを確認できるようになります。

> [!IMPORTANT]
> Teams は、ユーザーがオフラインのときや限られた帯域幅で実行しているときには、会議やライブ イベントをスケジュールできないようにします。 

| 確認事項 | アクション |
|--------------|--------|
| ミーティングの展開前および展開時に帯域幅の計画を実行する必要があるか? |詳細および計画プロセスを簡単にするツールへのリンクについては、「[ネットワークの準備](3-envision-evaluate-my-environment.md#network-readiness)」を参照してください。|
|||

### <a name="meeting-recording-and-archiving"></a>ミーティングの記録とアーカイブ

ユーザーは音声、ビデオ、および画面共有のアクティビティをキャプチャするために、ミーティングとグループの通話を記録できます。 自動的に文字起こしする記録のオプションもあるため、ユーザーはミーティングの記録を字幕付きで再生して、会議内容の重要な議題を検索できます。 記録はクラウドで実施され Microsoft Stream に保存されるため、ユーザーは組織全体で安全に議事録を共有できます。 ミーティングの記録を検索するには、ミーティングの会話に移動します。

>[!Note]
> Microsoft Stream の使用から[会議の記録用の OneDrive for Business および SharePoint ](tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。

詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。

| 確認事項 | アクション |
|--------------|--------|
| ミーティングの文字起こしサービスをオンにするか?|「[記録の文字起こしをオンまたはオフにする](cloud-recording.md#turn-on-or-turn-off-cloud-recording)」を参照してください。|
|||


### <a name="live-events-policies"></a>ライブ イベント ポリシー

Teams のライブ イベント ポリシーは、ユーザー グループのイベント設定を管理するために使用します。 既定のポリシーを使用することも、ライブ イベントを保持する組織内のユーザーに割り当て可能な追加のポリシーを作成することもできます。 

| 確認事項 | アクション |
|--------------|--------|
| 自分の組織は Teams のライブ イベントを使用するか?| Teams のライブ イベントの計画、設定、および構成に関する詳細については、[ライブ イベントの記事](teams-live-events/what-are-teams-live-events.md)を参照してください。|
|||

### <a name="conference-room-systems-rollout"></a>会議室システムの展開

多数の会議室を使用する組織は、会議室の一覧を作成して、適切なデバイスを特定し、それらを展開するための構造化された方法について検討することがあります。 



| 確認事項 | アクション |
|--------------|--------|
| 会議室システムを展開するために何を実行する必要があるか?|[Plan Microsoft Teams ルーム](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)の記事をご確認ください。|
|||

### <a name="cloud-video-interop"></a>クラウド ビデオ相互運用性

クラウド ビデオ相互運用性により、サード パーティ製の会議室デバイスで Teams のミーティングに参加することが可能になります。 

コンテンツの共同作業にかかわるビデオ会議では、会議を最大限に活用できます。 ただし、会議室システムとデバイスのアップグレードには高価な費用がかかります。 Teams のクラウド ビデオ相互運用性は、サード パーティ製のシステムと連動して、会議室または Teams のクライアントで、すべての参加者にネイティブなミーティング エクスペリエンスを提供します。 

| 確認事項 | アクション |
|--------------|--------|
| 会議室システムの展開の一部としてクラウド ビデオ相互運用性ソリューションを使用するか? | 「[Teams のクラウド ビデオ相互運用性](cloud-video-interop.md)」を参照してください。|
|||


### <a name="personal-device-rollout"></a>個人用デバイスの展開

ミーティングや音声通話の展開をサポートするために個人用デバイスの大規模な展開を計画するときには、再現可能な品質を提供する繰り返し可能なサイトごとの展開プロセスの使用を検討してください。

| 確認事項 | アクション |
|--------------|--------|
|ミーティングの展開にサイトごとのアプローチを使用するか? |  「[Teams のサイト有効化プレイブック](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads)」は、独自の展開に使用できる優れた基礎知識を提供しています。 このガイドは、音声通話に焦点を合わせていますが、デバイスの配布、アカウントの準備、導入、およびトレーニングに関する一般的な概念は、大規模なミーティングの展開に当てはまります。 |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>ミーティングと通話の品質に関するトラブルシューティング 

Teams では、通話品質の問題を監視してトラブルシューティングするために、[通話分析と通話品質ダッシュボード](monitor-call-quality-qos.md)という 2 つの方法を利用できます。 通話分析は、各ユーザーの特定の通話および会議に関連するデバイス、ネットワーク、および接続性についての詳細情報を示します。 通話分析は特定の通話の品質にかかわる問題を管理者やヘルプデスク エージェントがトラブルシューティングする際の支援を目的として設計されていますが、通話品質ダッシュボードは管理者やネットワーク エンジニアがネットワークを最適化する際の支援を目的として設計されています。 通話品質ダッシュボードは、特定のユーザーに焦点を合わせるのではなく、Teams 組織全体についての集計情報に注目します。 

|確認事項|アクション |
|------------|-------|
| 通話品質の問題についての監視およびトラブルシューティングを誰が担当するか? | 通話品質の問題をトラブルシューティングするために必要なアクセス許可レベルの詳細については、「[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)」を参照してください。|
|||

### <a name="operate-your-meetings-service"></a>ミーティング サービスの運用

Teams のサービスにかかわる全体的な正常性を把握して、サービスに影響を与えるあらゆるイベントについて組織内の他のユーザーに事前に警告できるようにすることが重要です。 「[サービスを運用する](1-drive-value-operate-my-service.md)」の記事には、サービスの運用に関する詳細なガイダンスが記載されています。

|確認事項|アクション |
|------------|-------|
|ミーティング サービスの管理を組織内の誰が担当するか? | この担当者には、ミーティング サービスを管理するために必要な Teams の管理者アクセス許可があることを確認してください。 Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。|
|||


## <a name="next-steps"></a>次のステップ
- 組織全体にミーティングと会議の[導入を推進する](adopt-microsoft-teams-landing-page.md)。
- [電話会議を追加する](deploy-audio-conferencing-teams-landing-page.md)
- [クラウド ボイスを展開する](cloud-voice-landing-page.md)
- お勧めのアプリ (Planner など) を Teams の初期ロールアウトに組み込む。 Teams 導入の進行に応じて、その他の[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を追加してください。
