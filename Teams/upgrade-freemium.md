---
title: Microsoft Teams 無料版 (クラシック)をサブスクリプションにアップグレードする
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
search.appverid: MET150
description: ユーザーの Microsoft 365 または Office 365 サブスクリプション プランを購入して、Microsoft Teams 無料版 (クラシック)から完全版に簡単にアップグレードする方法について説明します。
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
ms.openlocfilehash: f2b9a76cd5f202a0c7d9805e7c5742bc0a470c06
ms.sourcegitcommit: ff5411084dc34754462d5fd67b64db7a7e76f1e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2023
ms.locfileid: "69823256"
---
# <a name="upgrade-microsoft-teams-free-classic-to-subscription-version"></a>Microsoft Teams 無料版 (クラシック)をサブスクリプション バージョンにアップグレードする

> [!IMPORTANT]
> Microsoft Teams 無料版 (クラシック) ライセンスは非推奨となり、2023 年 4 月中旬から使用できなくなるので、Microsoft Teams 無料版 (クラシック)から Teams のサブスクリプション バージョンにアップグレードする必要があります。 この記事は、ユーザーを有料の Teams ライセンスにアップグレードする方法に関する手順で近日中に更新されます。

組織がMicrosoft Teams 無料版 (クラシック)を使用している場合は、ユーザーの Microsoft 365 または Office 365 サブスクリプション プランを購入することで、完全版に簡単にアップグレードできます。 フル バージョンでは、電話会議、拡張管理、セキュリティ機能など、無料版では提供されないその他の Teams 機能が提供されます。 Microsoft 365 と Office 365は、使い慣れた Microsoft Office デスクトップ スイートと、Exchange Online、SharePoint Online、Office などの Microsoft の次世代通信およびコラボレーション サービスのクラウドベースバージョンを組み合わせて、ユーザーがインターネットを通じてどこからでも生産性を高めるのに役立ちます。 Teams をアップグレードしても、既存の Teams データは失われません。すべてのチーム、チャネル、チャット、ファイル、アクセス許可が付属しています。

> [!NOTE]
> 既に Microsoft 365 または Office 365 サブスクリプションをお持ちの場合は、無料版ではなく、試用版 (会社の ID を使用) の対象となります。 Teams 試用版では、期間限定で Teams のフル バージョンが提供されます。 詳細については、「 [Microsoft Teams コマーシャル クラウド試用版オファーの管理](./teams-exploratory.md)」を参照してください。

## <a name="how-does-teams-free-classic-compare-to-the-full-version-of-teams"></a>Teams Free (クラシック) と Teams のフル バージョンの比較

Teams Free (クラシック) は、中小企業向けに設計されており、次の機能があります。

- 最大 500,000 人のユーザー
- 無制限のチャット メッセージと検索
- ゲスト アクセス
- Word、Excel、PowerPoint、OneNote のオンライン バージョンを含むアプリやサービスとの統合
- ユーザーあたり 2 GB のストレージと 10 GB の共有ストレージ
- 1:1 とグループのオンライン オーディオとビデオ通話
- チャネル会議
- 画面共有

Microsoft 365 または Office 365 サブスクリプションに含まれる Teams の完全版には、Microsoft Teams 無料版 (クラシック)が提供する機能に加えて、次の機能が用意されています。

- ユーザー制限なし (エンタープライズ ライセンスあり)
- Exchange メール ホスティングとカスタム メール ドメイン
- OneDrive、SharePoint、Planner、Yammer、その他の Microsoft 365 および Office 365 サービス
- ユーザーあたり 1 TB のストレージ
- 予約された会議
- 電話会議
- 多要素認証、シングル サインオン、監査 (Premium) とレポートなど、セキュリティとコンプライアンスの強化機能
- 24 x 7 の電話と Web サポート、ユーザーとアプリを管理するための管理ツール、Microsoft 365 または Office 365 サービスの使用状況レポート、サービス レベルアグリーメント、構成可能なユーザー設定とポリシーなど、管理コントロールとサポート機能

Teams Free (クラシック) 機能と Teams 機能の詳細な比較については、「 [Teams プランの比較](https://products.office.com/microsoft-teams/free)」を参照してください。

## <a name="upgrade-requirements"></a>アップグレード要件

次の要件を満たしている場合は、Teams のフル バージョンにアップグレードできます。

- 既存のMicrosoft Teams 無料版 (クラシック) サブスクリプションにサインアップしたユーザーです。
- 独自のドメインを持ち込む場合、(試用版または購入した Microsoft 365 または Office 365 サブスクリプションを使用して) Azure Active Directory にまだ関連付けられません。

> [!NOTE]
> データをアップグレードして転送するには、Teams アプリケーションのアップグレード プロセスを通じてサブスクリプションを購入する必要があります。 アップグレード プロセスを経ずに Teams で Microsoft 365 または Office 365を購入した場合は、既に別のテナントがあるため、データを転送できません。

## <a name="limitations"></a>制限事項

次の制限事項に留意してください。

- アップグレード後に Teams Free (クラシック) に切り替えることはできません。
- 複数の Teams Free (クラシック) テナントを 1 つの有料テナントにマージすることはできません。
- すべてのユーザーは同じドメインに属している必要があります。 (すべてのユーザーが *ユーザー名*@の形式でサインインします *domain.com*.)
- すべてのユーザーをアップグレードする必要があります。同じテナント内の Teams Free (クラシック) ユーザーと有料サブスクリプション ユーザーの組み合わせはサポートされていません。

## <a name="how-do-i-upgrade-my-organization"></a>組織をアップグレードするにはどうすればよいですか?

Teams のフル バージョンにアップグレードするには、[Teams で **アップグレード** ] を選択します。

![[アップグレード] ボタンを示すスクリーンショット。](media/teams-freemium-upgrade-image1.png)

Teams へのサインインに使用するメール アドレスを入力し、Microsoft 365 Business Standard プランを購入します。 Microsoft 365 Business Basicまたはエンタープライズ エディションのOffice 365を購入する場合は、[サポートにお問い合わせください](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade)。

## <a name="whats-next"></a>次は何ですか?

アップグレードが完了したら、最初の手順については [「Microsoft Teams の概要](get-started-with-teams-quick-start.md) 」と「組織全体の Teams 導入に対する段階的なアプローチに [Microsoft Teams](adopt-microsoft-teams-landing-page.md) を採用する」を参照してください。

## <a name="more-information"></a>詳細情報

- Teams のバージョンとその機能の詳細については、「 [Teams プランの比較](https://products.office.com/microsoft-teams/free)」を参照してください。
- Teams のフル バージョンへのアップグレードの詳細については、「 [Teams Free (クラシック) から Teams へのアップグレード](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39)」を参照してください。
- ユーザー ライセンスの追加、ユーザー名の変更、一時的なパスワードの割り当てなど、ユーザーのアップグレードに関連するその他の管理タスクについては、「 [Teams Free (クラシック) から有料サブスクリプションへの管理者のアップグレード](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52)について」を参照してください。
- 組織内で無料の Teams を管理する方法の詳細については、「 [Microsoft Teams Free (クラシック) の管理](manage-freemium.md)」を参照してください。
