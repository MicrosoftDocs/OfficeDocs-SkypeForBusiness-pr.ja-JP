---
title: 組織の Microsoft Teams をサポートする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.custom: seo-marvel-mar2020
ms.reviewer: marcl, billkau
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: チーム管理者またはヘルプデスクサポートエンジニアのいずれかにかかわらず、組織内の Microsoft Teams をサポートするのには、これらのリソースを使用します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cde06d104f6f61efd981bb87b1503e8f097c5c26
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637036"
---
# <a name="support-microsoft-teams-in-your-organization"></a>組織の Microsoft Teams をサポートする

> [!NOTE]
> この記事は、Teams の既知の問題に関する記事を置き換えるものです。 

組織のチームをサポートするには、この記事にあるリソースを使用します。 

最初に、この記事で後述する最も多かった [一般的な問題と解決方法](#common-issues-and-resolutions) リストの確認から開始します。

次に、必要なものが見つからない場合は、[チームのトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) に移動して、目次の問題を検索するか、**[タイトル別にてフィルターをかける ]** ボックスの問題を検索します。 
:::image type="content" source="media/known-issues1.png" alt-text="チームのトラブル シューティング ページにある [目次とフィルター] ボックスのスクリーンショット":::

それでも問題が解決しない場合は、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)にお問い合わせください。


## <a name="common-issues-and-resolutions"></a>一般的な問題と解決策

> [!NOTE]
> COVID-19 の影響により、リモート ワーカー (WFH) をサポートするために Teams の展開に関してサポートが必要な場合は、「[Teams を使用してリモート ワーカーをサポートする](support-remote-work-with-teams.md)」をご覧ください。 また、Microsoft 365 FastTrack プログラムから展開についてのサポートを受けることもできます。リクエストを送信する方法については、[FastTrack センター](https://www.microsoft.com/fasttrack)を参照してください。

### <a name="for-all-teams-customers"></a>すべての Teams のお客様

| |  |
|---------|---------|
|**Teams は初めてですか?**    |「[Microsoft Teams の使用を開始する](get-started-with-teams-quick-start.md)」をご覧ください。         |
|**Teams のゲスト アクセスを有効にする**     |「[Teams のゲスト アクセス チェックリスト](guest-access-checklist.md)」を確認し、すべての手順が完了したことを確認します。 以下の追加リソースを参照してください。<ul><li>[Microsoft Teams でのゲスト アクセスについて](guest-access.md)</li>[ゲストがチームに参加する方法](guest-joins.md) <li>[セットアップ – Microsoft Teams のゲスト アクセスのチェックリスト](guest-access-checklist.md)</li></ul>|
|**Teams での会議とダイヤルイン**    |Teams で電話会議を有効にしたり、設定したりする方法について、サポートをご希望ですか? このユーザーを最近作成しましたか? そうであれば、**設定が有効になるまで**、2 から 24 時間待つ必要があります。<br>そのユーザーに電話会議のライセンスが与えられ、既定の有料電話番号があることを確認するには、次のようにします。<br><ol><li>Microsoft 365 管理センターで、**[アクティブなユーザー]** に移動し、問題のユーザーを選択します。</li><li> 管理センター バージョンに応じて、**[ライセンスとアプリ]** を選択するか、**製品ライセンス**の **[編集]** をクリックします。</li><li> ユーザーに、電話会議、Microsoft Teams、Skype for Business Online (プラン 2) 用に選択したライセンスがあることを確認します。</li><li>ユーザー**管理センター**で、**[すべて表示]**、**[Teams]** の順にクリックします。</li><li>Microsoft Teams 管理センターで、**[従来のポータル]** をクリックします。</li><li>Skype for Business 管理センターで、**[電話会議]**、**[ユーザー]** の順にクリックします。</li><li>該当するユーザーを選択し、そのユーザーに既定の有料電話番号があることを確認します。</li> </ol> 詳細については、「[通話プラン](calling-plans-for-office-365.md)」を参照するか、ライセンス関連の質問について Microsoft コマース課金チームにお問い合わせください。 <br><br>追加情報:<ul><li>[Microsoft Teams でのミーティングと会議](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[電話会議](audio-conferencing-in-office-365.md)</li></ul>       |
|**Teams Exploratory ライセンス**     |Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (AAD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。 管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。 以前の [Microsoft の商用クラウド試用版](iw-trial-teams.md) は、 Teams Exploratory エクスペリエンスに変更になりました。 <br><br>追加情報:<ul><li>[ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Teams Exploratory エクスペリエンスを管理する](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**プライベート チャネル**    |Microsoft Teams のプライベート チャネルは、チーム内でのコラボレーションのための集中スペースを作成します。 プライベート チャネルの所有者またはメンバーであるチームのユーザーのみがチャネルにアクセスできます。 既にチームのメンバーである限り、ゲストを含む全てのユーザーをプライベート チャネルのメンバーとして追加できます。<br><br>知る必要があるユーザーにコラボレーションを限定したい場合、または管理する追加のチームを作成せずに特定のプロジェクトに割り当てられたユーザーのグループの間のコミュニケーションを促進したい場合は、プライベート チャネルの使用がお勧めです。<br><br>追加情報:<ul><li>[ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Teams Exploratory エクスペリエンスを管理する](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**会議ポリシー**|[会議ポリシー](meeting-policies-in-teams.md)は、組織内のユーザーによってスケジュールされた会議への参加者が利用できる機能を制御するために使用されます。 ポリシーを作成して変更を行った後、ユーザーをポリシーに割り当てることができます。         |
||**会議ポリシーを変更または作成する**<br><br>会議ポリシーを変更または作成するには、Microsoft Teams 管理センターにアクセスし、[**会議**]  >  [**会議ポリシー**] の順に移動します。 一覧からポリシーを選択するか、[**追加**] を選択します。 新しいポリシーを作成する場合は、名前と説明を追加します。 名前に特殊文字を含めたり、64 文字より長くしたりすることはできません。 設定を選び、**[保存]** をクリックします。 たとえば、多数のユーザーがいて、会議に必要な帯域幅を制限するとします。 「制限された帯域幅」という名前の新しいカスタム ポリシーを作成し、次の設定を無効にできます。<br><br>[**オーディオとビデオ**] で、<ul><li>[クラウド記録を許可する] を無効にします。</li><li>[IP のビデオを許可する] を無効にします。</li></ul>[**コンテンツの共有**] で、<ul><li>画面共有モードを無効にします。</li><li>[ホワイトボードを許可] を無効にします。</li><li>[メモの共有を許可する] を無効にします。</li></ul>その後、ポリシーをユーザーに割り当てます。         |
| |**ユーザーに会議ポリシーを割り当てる**<br><br>1 人のユーザーに会議ポリシーを割り当てるには、次の操作を行います。<ol><li>Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</li><li>ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</li><li>[**会議ポリシー**] で割り当てるポリシーを選択し、[**適用**] をクリックします。</li></ol> 複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。 <ol><li>Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</li><li>[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</li><li>[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</li></ol>または、以下の操作を実行できます。<ol><li>Microsoft Teams 管理センターの左側のナビゲーションで、**[会議] > [会議ポリシー]** の順に移動します。</li><li>ポリシー名の左側をクリックしてポリシーを選びます。</li><li>**[ユーザーを管理する]** を選択します。</li><li>[**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。</li><li>ユーザーの追加が完了したら、**[保存]** をクリックします。</li></ol> ||**表示されないダイヤル パッドのトラブルシューティング**     |以下の操作を行います。 <ul><li>ユーザーに [Teams ライセンス](teams-add-on-licensing/assign-teams-add-on-licenses.md)が割り当てられていることを確認します。</li><li>ユーザーに[通話プラン](calling-plan-landing-page.md)が割り当てられていることを確認します。</li><li>[エンタープライズ VoIP](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail) に対してユーザーを有効にします。</li></ul>      ||**Teams サインインのトラブルシューティング**   |最初に、[Microsoft Teams サービスが正常である](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth)ことを確認します。 次に一般的なエラー コードを確認し、「[Microsoft Teams へのサインインで問題が起きるのはなぜですか。](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)」を参照します。  「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」の確認が必要となる場合もあります。         |

### <a name="for-education-customers"></a>教育機関のお客様

|||
|---------|---------|
|ユーザーに「使い損ねていますよ」という メッセージが表示される場合。   |「[学校の Microsoft Teams を有効にする](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)」を確認してください。 EDU テナントにおいて、既定では Teams は有効になっていません。最初に、Teams を有効にする必要があります。 <br><br>次に、「[リモート教育と学習](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4)」を参照して、学校向けのセットアップに関する最新のガイダンスやトレーニング計画、仮想授業、生徒とのコンテンツの共有について確認してください。<br><br>最後に Microsoft Teams IT 管理者トレーニング ビデオ、デッキ、その他の詳細を、「[Teams の管理者トレーニング](itadmin-readiness.md)」でご覧ください。        |


## <a name="related-topics"></a>関連項目

[チームのトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Teams のサポート リソース](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
