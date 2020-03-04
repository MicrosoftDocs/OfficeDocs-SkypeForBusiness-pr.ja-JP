---
title: 教育機関管理者向けの Microsoft Teams のリソース
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Microsoft Teams for EDU のリモート学習スタートアップガイダンス。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87d9e36578227c8f27acfdfd07abfa0cadbe69b7
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403839"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>リモート学習のための Microsoft Teams の使用を開始する

Microsoft Teams は、会話、コンテンツ、課題、アプリを1か所にまとめるプラットフォームです。 コラボレーティブな教室を構築し、専門的な学習コミュニティに接続し、同僚とつながりましょう。すべて1つの環境で利用できます。

この記事に記載されたベストプラクティスを使用して、リモート学習機能を有効にするには、教育ニーズに応じて Microsoft Teams の使用を開始します。 Microsoft Teams を使用すると、クラスのコラボレーションを可能にして、会話での学生の対話、仮想会議プラットフォームの提供、課題の配布を行うことができます。 学校の管理者とスタッフは、チームを使って最新の状態に維持して、お知らせや topical の会話を行うことができます。 教師は、専門的な学習コミュニティを利用して、教育機関向けの教材を共有できます。

Microsoft Teams には、すべてのスタッフと学生が確実に接続できるように、デスクトップ (Windows、Mac、Linux)、web、モバイル (Android および iOS) の[クライアント](get-clients.md)があります。

Microsoft Teams の利用状況の詳細については、「[教育機関向けの teams」を](https://aka.ms/TeamsEDUWebinars)参照してください。

## <a name="user-accounts-licenses-and-identity-security"></a>ユーザーアカウント、ライセンス、id セキュリティ

Microsoft Teams は Microsoft 365 機能を活用し、ユーザーを認証してサービスを提供します。 スタッフ、インストラクター、および学生は、共同作業を円滑に行うために id を確立する必要があります。 Id がまだ存在しない場合は、このプロセスに従って id を設定します。

Teams のライセンスを使用するには、ユーザーが teams の機能を使い始める前に有効にしておく[必要があり](user-access.md)ます。 チームは、コラボレーションシナリオを可能にするために、 [Office 365 グループ](Office-365-groups.md)、 [Exchange](Exchange-Teams-interact.md)、 [SharePoint、OneDrive](SharePoint-OneDrive-interact.md)などの Microsoft 365 のその他の機能に依存します。 これらのすべてのサービスが有効になっている場合、ユーザーは最良のチームエクスペリエンスを提供します。 [Google でホストされているメールを使用](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users)しているユーザーは、Teams をサポートしています。

## <a name="easily-set-up-microsoft-teams"></a>Microsoft Teams を簡単に設定する

Teams を起動して実行するには、次の2つの作業を行う必要があります。

### <a name="1-allow-users-to-create-teams"></a>1. ユーザーがチームを作成できるようにする

学生と教師は最小限の障壁でアプリを使うことができるため、チームを最大限に活用し、ニーズに合わせて柔軟にカスタマイズすることができます。 ユーザーがチームの操作をカスタマイズできる方法の1つとして、ニーズに合ったチームを作成できることが挙げられます。 **既定では、すべてのユーザーが Office 365 グループとチームを作成でき**ます。 この機能が適切でない場合もあります。たとえば、一部のお客様は、第1の学生によるチームの作成を制限したい場合があります。 必要に応じて、Office 365 グループおよびチームの作成は、環境内の[特定のセキュリティグループに制限](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)できます。

教育機関のお客様は、学生を含むすべてのユーザーに、クラス、研究、グループプロジェクト、研究グループのチームの作成を許可することができます。 プライマリ-セカンダリ学校では、学生が Teams の作成を制限して、成人を含むフォーラム内ですべての学生と学生間の通信が行われていることを確認したい場合があります。 この場合、Office 365 グループとチームの作成は、すべての教員および職員に制限されます。

### <a name="2-configure-user-experiences-using-policies"></a>2. ポリシーを使用してユーザーエクスペリエンスを構成する

[チームポリシー](teams-policies.md)は、特定のユーザーまたはユーザーのグループで利用可能なオプションを制御する機能を提供します。 ポリシーを適用して、プライベートチャットの使用を許可するユーザー、プライベート通話、会議のスケジュール、共有可能なコンテンツタイプを定義することができます。

既定の (グローバル) ポリシーに含まれている機能を活用して、**より高い教育スタッフ、教育者、および学生**が恩恵を受けることができます。 その他のポリシー設定を有効にして、Microsoft Teams の機能をさらに追加することができます。これには、[メッセージングポリシーでの翻訳機能の有効化](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)、会議ポリシーでの自動会議の議事録の自動実行が含まれます。

第**1 の学校の学生は、** 学生に提供される制限された機能を必要とする場合があります。 ポリシーによって、学生が実行できる操作の境界が設定されます。 学生の人口は、多くの場合、多くの場合、最も制限の厳しい設定であるため、学生のポリシーは、"グローバル (組織全体の既定)" ポリシーに変更することをお勧めします。

次に示すのは、一般的な既定以外のポリシー構成であり、学生間の unmoderated の通信を制限するために、第1の学生に割り当てられます。

#### <a name="messaging-policy"></a>メッセージングポリシー

- 設定を ' オフ ' に変更する
- Giphy コンテンツの評価が ' strict ' に設定
- "オン" に設定されるメッセージの翻訳
- 優先度通知を使って緊急メッセージを送信する
- グループチャットから「オフ」に設定してユーザを削除

#### <a name="meeting-policy"></a>会議ポリシー

- チャンネルの [今すぐ会議を許可する] を [オフ] に設定する
- Outlook アドインを ' オフ ' に設定する
- チャネル会議のスケジュールを ' オフ ' に設定できるようにする
- プライベート会議のスケジュールを ' オフ ' に設定できるようにする
- [プライベート会議の今すぐ会議を許可する] を [オフ] に設定します。

#### <a name="live-events-policy"></a>ライブイベントのポリシー

- スケジュールを ' オフ ' に設定する

#### <a name="calling-policy"></a>通話ポリシー

- プライベート通話を ' オフ ' に設定する

#### <a name="teams-policy"></a>Teams のポリシー

- "オフ" に設定したプライベートチャネルを作成する

学生に対して制限されている可能性がある主要な機能を付与する、**学校の主なスタッフおよび教育**者向けのポリシーを割り当てる必要があります。 プライベートチャットと会議のスケジュール設定 (新しいポリシーの既定の設定) を許可する新しいポリシーを作成します。 [セキュリティグループメンバーシップを使って、これらのポリシーをスタッフや教師に割り当て](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)ます。

## <a name="start-using-teams"></a>Teams の使用を開始する

### <a name="create-class-teams-for-secure-classroom-use"></a>セキュリティで保護された教室で使用するクラスチームを作成する

Microsoft Teams for エデュケーションは、教育機関向けの[特定のチームタイプ](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)を提供します。 [クラスチームの種類](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)は、課題、OneNote の教室ノートブック、学生用の読み取り専用コンテンツを保護するための[クラス素材フォルダー](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)など、特定の機能を備えた教室向けに設計されています。 クラスチームを展開するには、次の2つの方法があります。

1. School [Data Sync](https://sds.microsoft.com/) (SDS) を設定することで、school information system の情報に基づいて、クラスのチームをすべてのクラスに対し**て**作成できるようになります。 このプロセスでは、セクションごとにチームがプロビジョニングされ、インストラクターと学生の選手名簿の同期が維持されます。教師は、学生に admitting 前に[チームの準備を行うことができ](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)ます。 または、教師がチームを使っていない場合、教師は「ライセンス認証」をクリックしないため、チームには学生が許可されません。 SDS は、データのインポートに80のさまざまな School Information Systems (SIS システム) をサポートしており、 [sds のサポートチーム](https://aka.ms/SDSSupport)は計画と構成を支援する準備をしています。
1. **教師**は、独自のクラス型チームをセットアップし、学生を招待します。 学生は、[チームに学生を追加](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)したり、[参加コードを共有](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)したり、[チームへのリンクを共有](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)したりすることで、これを行うことができます。 可能であれば、学生をチームに追加することで、学生が確実にアクセスできるようにし、チームに追加されたことが通知されるようにすることをお勧めします。

チームをセットアップした後は、チームの所有者がチーム[の設定をカスタマイズ](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158)できます。たとえば、チームの[画像](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0)の追加、クラスのテーマの[チャネルの作成](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US)、グループのコラボレーション領域、Quizlet/Flipgrid/kahoot などの[アプリを追加](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77)して既存の教育コンテンツに参加し、全員に通知を[送信](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2)して会話を開始します。

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>スタッフのコミュニケーションとコラボレーションのためのスタッフチームを作成する

[スタッフの種類のチーム](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf)は、学校の管理者やスタッフが、お知らせの作成、会議の設定、コンテンツの共有、外部アプリ ([タスクのトラッキングの計画](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2)など) を行うなど、学校全体のイニシアチブで簡単に情報を共有し、共同作業を行うことができるように設計されています。 学校の管理者は、チームの作成ウィザードを使用して、チームの作成ウィザードでメンバーをチームに追加したり、[チームを作成した後でメンバーを追加](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)したり、[参加コードやチームへのリンクを共有](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)したりすることができます。 [チャネルを作成](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525)することは、ワークストリームまたは件名を使って会話やファイルを整理するのに最適な方法です。 [チーム所有者向けの移動ガイドは、](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US)チーム所有者の職務と機能について理解するのに最適な場所です。

## <a name="teams-meeting-scenarios"></a>Teams 会議のシナリオ

### <a name="collaborative-meetings-for-virtual-classes"></a>仮想クラスのコラボレーション会議

[Microsoft Teams 会議](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams)では、音声、ビデオ、[コンテンツ共有](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7)、ホワイトボード、共有ノートを使用できる機能など、最大250人の同時出席者をサポートしています。 Microsoft Teams クライアントで[は、プライベートスペースまたはチームチャネル内で会議](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams)をスケジュールすることができます。これにより、チームメンバー全員がそのことを把握できます。 会議を記録して出席者が後で確認できるように保存することができます。 これらの記録は、ディスカッションされた[コンテンツを簡単に見つけるために transcribed](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308)することもできます。 会議にはノート pc または携帯電話の web カメラ、マイク、スピーカーを使用できます。また、 [Microsoft Teams で最適化](https://products.office.com/microsoft-teams/across-devices/devices)されたデバイスからプレミアム音声/ビデオ品質を取得できます。

### <a name="districtuniversity-events-or-updates"></a>ディストリクト/大学のイベントまたは更新

一部の命令には、より多くのユーザーが必要であり、追加の運用機能が必要です。 このような会議では、発表者、プロデューサー、モデレートの Q&A に定義されていることがよくあります。 Microsoft Teams では、 [Microsoft teams のライブイベント](teams-live-events/what-are-teams-live-events.md)を使って、これらのセッションをサポートしています。 ライブイベントは、学区または大学全体の更新プログラム、リーダーシップの住所、大規模なクラスまたは学生グループへの指示、またはコミュニティに拡張するシナリオに使用できます。 ライブセッションの実施の詳細については、「[ライブイベントの計画とスケジュール設定](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)」、「ライブイベントの[生成](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb)」、「[ライブイベント](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)への参加」、「 [Q&の調停](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)」を参照してください。

## <a name="recommended-tips--tricks"></a>推奨されるヒント & テクニック

Microsoft Teams の教育機関向けの使用方法については、「[教育機関向けの Microsoft teams](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114)」を参照してください。

> [!NOTE]
> Microsoft Teams の主な機能については、教育機関向けのものではありません。 主要なチーム機能のヒントとテクニックについては、「 [Microsoft Teams のヘルプと学習](https://support.office.com/teams)」を参照してください。

## <a name="adoption-content"></a>導入コンテンツ

Microsoft は、Microsoft Teams を展開するための[導入コンテンツ](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)と戦略ガイダンスを開発しました。 [Microsoft Teams の導入ガイド](https://teamworktools.azurewebsites.net/tft/index.html)には、利用可能なコンテンツの概要と[チームのカスタマーサポートキット](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)が用意されており、チームの認識に使用できる多くのテンプレートが用意されています。 Microsoft 教師センターでは、 [Microsoft Teams](https://education.microsoft.com/learningPath/18793af1)と[OneNote](https://education.microsoft.com/learningPath/b6e3b5f2)を教室でどのように使用するかに関する教育機関向けのトレーニングを提供しています。

追加の導入リソースには次のものがあります。

- ["利用可能時間:90" クイックヒントビデオ](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Microsoft Teams for 教育ビデオのプレイリスト](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [ブログ: この学校で、距離学習のために Teams をどのように使用するかを確認する](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>サポートの準備

IT プロフェッショナルとサポートスタッフは、Microsoft Teams IT アーキテクチャポスターと管理者テクニカルトレーニングを利用して、チームのアーキテクチャと、Microsoft 365 の基本機能を使用することによって速度を向上させることができます。

追加のサポートリソースには次のものがあります。

- [Microsoft Teams のインストールと更新に関する問題のトラブルシューティング](troubleshoot-installation.md)
- [通話品質を監視および管理する](monitor-call-quality-qos.md)
- [Teams のサービス正常性を確認する](service-health.md)
- [Teams のサポート リソース](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [通話品質を監視および管理する](monitor-call-quality-qos.md)
- [Teams のサービス正常性を確認する](service-health.md)
- [Teams のサポート リソース](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Microsoft Teams のヘルプセンター](https://support.office.com/en-us/teams)
