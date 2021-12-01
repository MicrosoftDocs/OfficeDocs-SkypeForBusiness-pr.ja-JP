---
title: Free (Microsoft Teams) をサブスクリプションにアップグレードする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
search.appverid: MET150
description: ユーザーの Microsoft 365 または Office 365 サブスクリプション プランを購入して、無料バージョンの Microsoft Teams から完全版に簡単にアップグレードする方法について学習します。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: d513a681b925f855d9354f517920a22003767eab
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257388"
---
# <a name="upgrade-microsoft-teams-free-classic-to-subscription-version"></a>Free Microsoft Teams (クラシック) をサブスクリプション バージョンにアップグレードする

組織で無料バージョンの Microsoft Teams を使用している場合は、ユーザーの Microsoft 365 または Office 365 サブスクリプション プランを購入することで、完全版に簡単にアップグレードできます。 完全版では、無料Teams提供されていない追加の機能 (スケジュール設定、電話会議、強化された管理、セキュリティ機能など) が提供されます。 Microsoft 365とOffice 365使い慣れた Microsoft Office デスクトップ スイートと、microsoft の次世代通信およびコラボレーション サービス (Exchange Online、SharePoint Online、Office など) のクラウドベースのバージョンを組み合Office — ユーザーがインターネットを介して事実上どこからでも生産的に作業を行えるのを支援します。 Teams をアップグレードすると、既存の Teams データが失われることはありません。すべてのチーム、チャネル、チャット、ファイル、およびアクセス許可が提供されます。

> [!NOTE]
> Microsoft 365 または Office 365 サブスクリプションを既に持っている場合は、無料版ではなく、(会社の ID を持つ) Teams の試用版の対象となります。 このTeams試用版では、一部の期間Teamsバージョンの完全版が提供されます。 詳細については、「Commercial [Cloud Trial オファーの管理Microsoft Teams」を参照してください](./teams-exploratory.md)。

## <a name="how-does-teams-free-classic-compare-to-the-full-version-of-teams"></a>Free (Teams) と完全バージョンのバージョンとの比較Teams。

Teams Free (クラシック) は、中小企業向けであり、次の機能があります。

- 最大ユーザー数は 500,000 人
- 無制限のチャット メッセージと検索
- ゲスト アクセス
- オンライン バージョンの Word、Excel、PowerPoint、アプリやサービスOneNote
- ユーザーあたり 2 GB のストレージと 10 GB の共有ストレージ
- 1:1 およびオンライン 音声通話とビデオ通話をグループ化する
- チャネル会議
- 画面共有

Teams Microsoft 365 または Office 365 サブスクリプションに含まれる完全なバージョンの Microsoft 365 には、無料で提供される機能に加えて、次Teamsがあります。

- ユーザー制限なし (エンタープライズ ライセンスを使用)
- Exchangeホスティングとカスタム メール ドメインを作成する
- OneDrive、SharePoint、Planner、Yammer、その他のMicrosoft 365サービスOffice 365。
- ユーザーあたり 1 TB のストレージ
- スケジュールされた会議
- 電話会議
- 多要素認証、シングル サインオン、高度な監査とレポートなど、セキュリティとコンプライアンスの強化された機能
- 24 x 7 の電話と Web のサポート、ユーザーとアプリを管理するための管理ツール、Microsoft 365 または Office 365 サービスの使用状況レポート、サービス レベル アグリーメント、構成可能なユーザー設定とポリシーなど、管理コントロールとサポート機能

Free (クラシック) 機能と Teams機能の詳細な比較については、「Teamsプランの比較[」をTeamsしてください](https://products.office.com/microsoft-teams/free)。

## <a name="upgrade-requirements"></a>アップグレードの要件

次の要件を満たしている場合は、Teamsバージョンにアップグレードできます。

- 既存の無料サブスクリプションにサインアップしたTeamsユーザーです。
- 独自のドメインを持ち込む場合は、(試用版または購入したドメインまたはサブスクリプションを使用して) Azure Active Directory に関連付Microsoft 365関連付Office 365されません。

> [!NOTE]
> データをアップグレードして転送するには、アプリケーションのアップグレード プロセスを通じてサブスクリプションを購入Teamsがあります。 アップグレード プロセスを行わずに Microsoft 365 または Office 365 を Teams で購入した場合は、既に別のテナントを持つため、データを転送できません。

## <a name="limitations"></a>制限事項

次の制限事項に注意してください。

- アップグレード後に無料 (クラシック) Teamsに切り替えはできない。
- Free (クラシック) テナントTeams複数のテナントを 1 つの有料テナントにマージできません。
- すべてのユーザーが同じドメインに入る必要があります。 (すべてのユーザーは、ユーザー名の形式でサインイン *を取得します。* @*domain.com*.)
- すべてのユーザーをアップグレードする必要があります。同じテナント内の無料 (クラシック) Teams有料サブスクリプション ユーザーの組み合わせはサポートされていません。

## <a name="how-do-i-upgrade-my-organization"></a>組織をアップグレードする方法

バージョン全体にアップグレードするには、Teams **で**[アップグレード] をTeams。

![[アップグレード] ボタンを示すスクリーンショット。](media/teams-freemium-upgrade-image1.png)

サインインに使用するメール アドレスを入力しTeamsプランを購入Microsoft 365 Business Standardします。 アプリまたはエディションの Microsoft 365 Business Basicを購入Enterprise場合は、Office 365[にお問い合わせください](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade)。

## <a name="whats-next"></a>次は何ですか?

アップグレードが完了したら、最初の手順については[「Microsoft Teams](get-started-with-teams-quick-start.md)の使用」と「Microsoft Teams[](adopt-microsoft-teams-landing-page.md)を導入する」を参照して、組織全体で導入をTeams段階的に行います。

## <a name="more-information"></a>詳細情報

- バージョンとその機能の詳細Teamsプランの比較に関する[ページTeamsしてください](https://products.office.com/microsoft-teams/free)。
- バージョン全体へのアップグレードの詳細については、「Teams [Free (クラシック)](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39)から Teams へのアップグレード」を参照Teams。
- ユーザー ライセンスの追加、ユーザー名の変更、一時パスワードの割り当てなど、ユーザーのアップグレードに関連する追加の管理タスクについては[、「Teams Free (クラシック)](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52)から有料サブスクリプションにアップグレードする管理者向け」を参照してください。
- 組織で無料の Teamsの管理については、「無料バージョンの管理」を参照[Microsoft Teams。](manage-freemium.md)