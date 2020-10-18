---
title: 電話会議の設定－Microsoft Teams
ms.reviewer: ''
description: ここに示す展開リソースを使用して、Microsoft Teams のミーティング ワークロードの一部として電話会議を展開してください。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 755a8499f62e39333b075519cc181dbd7c44e143
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521624"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>Microsoft Teams での電話会議の導入方法

電話会議とは、通常の電話機から Teams のミーティングに参加することと、ミーティングから電話番号に向けてダイヤルアウトすることができる機能です。 組織に電話会議を展開する際の一環として、[ミーティングの展開](deploy-meetings-microsoft-teams-landing-page.md)を確認しておいてください。

## <a name="audio-conferencing-deployment-decisions"></a>電話会議の展開に関する決定事項

この記事では、自分の組織のプロファイルとビジネスの要件に基づいて既定の電話会議の設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。 設定については 2 つのグループに分けて、まず、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分について説明します。 2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。

電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。 ダイヤルインするミーティングの参加者には、ライセンスの割り当てなど一切のセットアップが不要です。 ミーティングへのダイヤルイン (通話) は、外出先でラップトップやモバイル デバイスの Skype for Business または Teams アプリを使用してミーティングに参加できないユーザーにとって便利なものです。 


## <a name="audio-conferencing-prerequisites"></a>電話会議の前提条件 

Teams の電話会議を展開する前に、次の事項について検討してください。

|確認事項|アクション |
|------------|-------|
|自分の国/地域で電話会議が使用できるか?|自分の国/地域で電話会議が使用できるかどうかを調べるには、「[電話会議および通話プランを利用可能な国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。|
|ユーザーは Teams の電話会議に対応したライセンスを所持しているか?|電話会議のライセンスは、 Microsoft 365 または Office 365 E5 サブスクリプションの一部として入手できます。また、Microsoft 365 Business Standard、E1、または E3 サブスクリプションのアドオン サービスとしても入手できます。 <ul><li>ライセンスを取得して割り当てる場合は、「[Microsoft 365 または Office 365 の電話会議を試用または購入する](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)」および「[Microsoft 365 Apps for business　のライセンスを割り当てまたは削除する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」を参照してください。</li><li> 詳細は、[Microsoft Teamsアドオンライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)をご覧ください。 </li><li>それぞれのプランに含まれているクラウド機能を確認するには、「[プランに応じたライセンス オプション](teams-add-on-licensing/office-365-business-premium.md)」を参照してください。</li></ul>|
|電話会議のライセンスを割り当てたユーザーにコミュニケーション クレジットを購入する必要があるか?|詳細については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してから、この後のセクション「[コミュニケーション クレジット](#communications-credits)」を確認してください。|
|||


## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

電話会議の前提条件を満たしたら、次の作業を実行してユーザーの電話会議を構成します。


### <a name="teams-administrators"></a>Teams の管理者

Teams には、組織に適した Teams の管理に使用できる、カスタムの管理者の役割のセットが用意されています。 この役割によって、さまざまな機能が管理者に提供されます。 

| 確認事項 | アクション |
|--------------|--------|
|Teams 通信管理者の役割を誰に割り当てるか?|Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。|
|Teams 通信サポート エンジニアの役割を誰に割り当てるか?|管理者の役割を割り当てるには、「[Active Directory で管理者の役割と管理者以外の役割をユーザーに割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。|
|Teams 通信サポート スペシャリストの役割を誰に割り当てるか?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>会議ブリッジと電話番号

会議ブリッジにより、ユーザーは電話機を使用してミーティングにダイヤルインできるようになります。 会議ブリッジの既定の設定を使用することも、電話番号 (有料ダイヤル/無料ダイヤル) およびその他の設定 (PIN や使用言語など) を変更することもできます。

詳細については、「[電話会議](audio-conferencing-in-office-365.md)」を参照してください。

|確認事項|アクション |
|------------|-------|
|新しい会議ブリッジ番号を追加する必要があるか?| 新しい番号を追加する場合は、「[サービスの電話番号を取得する](/microsoftteams/getting-service-phone-numbers)」を参照してください。|
|ブリッジの設定を変更する必要があるか?|ブリッジの設定を変更する場合は、「[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)」を参照してください。|
|電話会議で使用する番号を移行する必要があるか?|電話番号の移行の詳細は、「[Teams に電話番号を転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。|
|||


### <a name="default-and-alternate-languages"></a>既定の言語と第 2 言語

Teams の電話会議では、会議ブリッジの既定の言語と第 2 言語を設定できます。

|確認事項|アクション |
|------------|-------|
| どの言語を自動応答案内に選択する必要があるか? | 言語を選択する場合は、「[電話会議の自動案内の言語を設定する](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」を参照してください。|
|||

### <a name="conferencing-bridge-settings"></a>会議ブリッジの設定 

会議ブリッジのセットアップ後 (既定および第 2 言語のセットアップを含む)、参加/退出の通知と使用する PIN の長さが適切かなど、既定の設定を確認します。 適切でない場合は変更できます。 

|確認事項|アクション |
|------------|-------|
| ユーザーがミーティングに参加または退出したときに参加者に通知するか? | これに該当する設定を変更する場合は、「[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)」を参照してください。|
|ミーティングの主催者がミーティングを開始するために使用する PIN に要求される長さは?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>ミーティングを主催するユーザーのダイヤルイン電話番号の設定

電話会議ブリッジの作成後、ミーティングの主催者が使用する有料ダイヤル番号や無料ダイヤル番号を設定する必要があります。

|確認事項|アクション |
|------------|-------|
| ミーティングを主催するユーザーごとに、どの会議ブリッジ番号を割り当てるか? | ダイヤルイン電話番号をユーザーに割り当てる場合は、「[手順 7: 会議を主催するユーザーにダイヤルイン電話番号を割り当てる](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings)」を参照してください。 |
|||

### <a name="communications-credits"></a>コミュニケーション クレジット

無料ダイヤルの会議ブリッジ電話番号を提供したり、国際電話番号への会議ダイヤルアウトをサポートするには、組織の通信クレジットをセットアップする必要があります。 コミュニケーション クレジットの詳細については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してください。

|確認事項|アクション |
|------------|-------|
|電話会議の実装にコミュニケーション クレジットが必要か? |コミュニケーション クレジットのセットアップが必要かどうかを調べるには、「[組織向けにコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。|
|必要な場合、購入金額はいくらにするか?|コミュニケーション クレジットの金額を判断する場合は、「[推奨される資金額](what-are-communications-credits.md#recommended-funding-amounts)」を参照してください。|
|自動リチャージする金額を構成できるか?|自動リチャージする金額を設定する場合は、「[組織のコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。|
|||



## <a name="additional-deployment-decisions"></a>その他の展開に関する決定事項

次の設定は、組織のニーズと構成に基づいて変更できます。

### <a name="outbound-calling-restriction-policies"></a>発信通話の制限ポリシー 

管理者は、発信通話の制御を使用して、組織内のユーザーが発信できる電話会議の種類とエンド ユーザーの PSTN 通話を制限できます。

|確認事項|アクション |
|------------|-------|
| 許可する発信通話の種類を制限するか? | 発信通話を制限する場合は、「[電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー](outbound-calling-restriction-policies.md)」を参照してください。|
|||


### <a name="dial-plans"></a>ダイヤル プラン

Microsoft 365 または Office 365 の電話システムの一部であるダイヤル プランは、通話の認証およびルーティングの目的で、ダイヤルされた電話番号を代替形式 (通常、E.164 形式) に変換する正規化ルールです。

ダイヤル プランの詳細については、「[ダイヤル プランについて](what-are-dial-plans.md)」を参照してください。

|確認事項|アクション |
|------------|-------|
|組織はダイヤル プランのカスタマイズを必要としているか?|カスタムのダイヤル プランが必要かどうかを判断する場合は、「[テナント ダイヤル プランの計画](what-are-dial-plans.md#planning-for-tenant-dial-plans)」を参照してください。 |
|どのユーザーがダイヤル プランのカスタマイズを要求していて、どのテナント ダイヤル プランを各ユーザーに割り当てる必要があるか?|PowerShell を使用して、カスタマイズしたダイヤル プランにユーザーを追加するには、「[ダイヤル プランの作成と管理](create-and-manage-dial-plans.md)」を参照してください。|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>ミーティングと通話の品質に関するトラブルシューティング 

Teams では、通話品質の問題を監視してトラブルシューティングするために、[通話分析と通話品質ダッシュボード](monitor-call-quality-qos.md)という 2 つの方法を利用できます。 通話分析は、各ユーザーの特定の通話および会議に関連するデバイス、ネットワーク、および接続性についての詳細情報を示します。 通話分析は特定の通話の品質にかかわる問題を管理者やヘルプデスク エージェントがトラブルシューティングする際の支援を目的として設計されていますが、通話品質ダッシュボードは管理者やネットワーク エンジニアがネットワークを最適化する際の支援を目的として設計されています。 通話品質ダッシュボードは、特定のユーザーに焦点を合わせるのではなく、Teams 組織全体についての集計情報に注目します。 

|確認事項|アクション |
|------------|-------|
| 通話品質の問題についての監視およびトラブルシューティングを誰が担当するか? | 通話品質の問題をトラブルシューティングするために必要なアクセス許可レベルの詳細については、「[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)」を参照してください。|
|||


## <a name="next-steps"></a>次のステップ
- 組織での電話会議の[導入を推進する](adopt-microsoft-teams-landing-page.md)。
- [クラウド ボイスを展開する](cloud-voice-landing-page.md)
- お勧めのアプリ (Planner など) を Teams の初期ロールアウトに組み込む。 Teams 導入の進行に応じて、その他の[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を追加してください。
