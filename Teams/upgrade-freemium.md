---
title: Microsoft Teams無料 (クラシック) をサブスクリプションにアップグレードする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
search.appverid: MET150
description: ユーザーのMicrosoft 365またはOffice 365サブスクリプション プランを購入して、無料版のMicrosoft Teamsからフル バージョンに簡単にアップグレードする方法について説明します。
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
ms.openlocfilehash: d3d9520952cb7a5e47d064341d09b655336ffda3
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031882"
---
# <a name="upgrade-microsoft-teams-free-classic-to-subscription-version"></a>Microsoft Teams無料 (クラシック) をサブスクリプション バージョンにアップグレードする

組織で無料版のMicrosoft Teamsを使用している場合は、ユーザーのMicrosoft 365またはOffice 365サブスクリプション プランを購入することで、完全版に簡単にアップグレードできます。 フル バージョンには、スケジュール設定、電話会議、強化された管理、セキュリティ機能など、無料版では提供されない追加のTeams機能が用意されています。 Microsoft 365とOffice 365は、使い慣れたMicrosoft Officeデスクトップ スイートと、Exchange Online、SharePoint Online、Officeなど、Microsoft の次世代の通信およびコラボレーション サービスのクラウドベースバージョンを組み合わせたものです。 — ユーザーがインターネットを介して事実上どこからでも生産性を高めるのに役立ちます。 Teamsをアップグレードすると、既存のTeams データが失われるわけではありません。すべてのチーム、チャネル、チャット、ファイル、アクセス許可が付属しています。

> [!NOTE]
> Microsoft 365またはOffice 365サブスクリプションが既にある場合は、無料版ではなく、(会社の ID を使用して) Teamsの試用版の対象となります。 Teams試用版では、限られた期間の完全なバージョンのTeamsが提供されます。 詳細については、「[Microsoft Teams Commercial Cloud Trial オファーの管理](./teams-exploratory.md)」を参照してください。

## <a name="how-does-teams-free-classic-compare-to-the-full-version-of-teams"></a>Teams Free (クラシック) は、Teamsのフル バージョンとどのように比較されますか?

Teams Free (クラシック) は、中小企業向けに設計されており、次の機能があります。

- 最大ユーザー数 500,000 人
- 無制限のチャット メッセージと検索
- ゲスト アクセス
- Word、Excel、PowerPoint、OneNoteの Online バージョンを含むアプリやサービスとの統合
- ユーザーあたり 2 GB のストレージと 10 GB の共有ストレージ
- 1:1 とグループのオンラインオーディオとビデオ通話
- チャネル会議
- 画面共有

Microsoft 365またはOffice 365サブスクリプションに含まれる完全なバージョンのTeamsには、無料で提供される機能に加えて、次Teams機能が用意されています。

- ユーザー制限なし (エンタープライズ ライセンスあり)
- Exchange電子メール ホスティングとカスタム電子メール ドメイン
- OneDrive、SharePoint、Planner、Yammer、その他のMicrosoft 365およびOffice 365 サービス
- ユーザーあたり 1 TB のストレージ
- 予約された会議
- 電話会議
- 多要素認証、シングル サインオン、監査 (プレミアム)、レポート作成など、セキュリティとコンプライアンスの強化された機能
- 24 x 7 の電話および Web サポート、ユーザーとアプリを管理するための管理ツール、Microsoft 365またはOffice 365 サービスの使用状況レポート、サービス レベル アグリーメント、構成可能なユーザー設定とポリシーなど、管理コントロールとサポート機能

Teams Free (クラシック) 機能とTeams機能の詳細な比較については、「[Teamsプランの比較](https://products.office.com/microsoft-teams/free)」を参照してください。

## <a name="upgrade-requirements"></a>アップグレードの要件

次の要件を満たしている場合は、Teamsのフル バージョンにアップグレードできます。

- あなたは、既存のTeams無料サブスクリプションにサインアップしたユーザーです。
- 独自のドメインを持ち込む場合は、(試用版または購入されたMicrosoft 365またはOffice 365サブスクリプションを使用して) Azure Active Directoryに関連付けられていない。

> [!NOTE]
> データをアップグレードして転送するには、Teams アプリケーションのアップグレード プロセスを通じてサブスクリプションを購入する必要があります。 アップグレード プロセスを実行せずにTeamsでMicrosoft 365またはOffice 365を購入した場合は、既に別のテナントがあるため、データを転送できません。

## <a name="limitations"></a>制限事項

次の制限事項に留意してください。

- アップグレード後、Teams Free (クラシック) に切り替えることはできません。
- 複数のTeams Free (クラシック) テナントを 1 つの有料テナントにマージすることはできません。
- すべてのユーザーは同じドメインに属している必要があります。 (すべてのユーザーは、*ユーザー名*@の形式でサインインを取得します。*domain.com*.)
- すべてのユーザーをアップグレードする必要があります。Teams Free (クラシック) ユーザーと、同じテナント内の有料サブスクリプション ユーザーの組み合わせはサポートされていません。

## <a name="how-do-i-upgrade-my-organization"></a>組織をアップグレードするにはどうすればよいですか?

Teamsの完全バージョンにアップグレードするには、Teamsで **[アップグレード**] を選択します。

![[アップグレード] ボタンを示すスクリーンショット。](media/teams-freemium-upgrade-image1.png)

Teamsへのサインインに使用するメール アドレスを入力し、Microsoft 365 Business Standard プランを購入します。 Microsoft 365 Business BasicまたはOffice 365のEnterpriseエディションを購入する場合は、[サポートにお問い合わせください](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade)。

## <a name="whats-next"></a>次は何ですか?

アップグレードが完了したら、最初の手順については[Microsoft Teamsに関する概要](get-started-with-teams-quick-start.md)を参照し、組織全体で導入[をTeams](adopt-microsoft-teams-landing-page.md)する段階的なアプローチについてはMicrosoft Teamsを採用します。

## <a name="more-information"></a>詳細情報

- Teamsバージョンとその機能の詳細については、「[Teamsプランの比較](https://products.office.com/microsoft-teams/free)」を参照してください。
- フル バージョンのTeamsにアップグレードする方法の詳細については、「[Teams Free (クラシック) から Teams へのアップグレード」を](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39)参照してください。
- ユーザー ライセンスの追加、ユーザー名の変更、一時パスワードの割り当てなど、ユーザーのアップグレードに関連するその他の管理者タスクについては、「[Teams Free (クラシック) から有料サブスクリプションにアップグレードする管理者向け](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52)」を参照してください。
- 組織内で無料でTeams管理する方法については、「[Microsoft Teamsの無料版を管理する](manage-freemium.md)」を参照してください。