---
title: Microsoft Teams の概要
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Microsoft Teams とそのインフラストラクチャについて、および Office 365 と組み合わせた Teams の使用について説明します。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86698a3bb7535a20b7fb1b6833062d118f2f9eae
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967130"
---
<a name="overview-of-microsoft-teams"></a>Microsoft Teams の概要
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


Microsoft Teams は Office 365 のすべてをまとめ、チームワークを遂行する上でチャットベースのハブをもたらし、よりオープンで、スムーズで、デジタルな環境を創り出す機会をお客様に提供します。Microsoft Teams は、Office 365 グループによって作られた既存の Microsoft テクノロジーを基に作られています。 

革新的な発想により、Teams は、Azure Active Directory (Azure AD) に保存された ID を利用し、Office 365 のその他のサービスと統合して、作成されるチームごとに SharePoint オンライン サイトと Exchange Online グループ メールボックスを作成します。

ビジネスやコンシューマー電子メール アカウントを Outlook、Gmail、またはその他のユーザーなど、すべてのユーザーは、チームにゲストとして参加できます。 来園者は Azure AD 内で安全に管理できるし、同じコンプライアンスと監査の保護として、Office 365 の残りの部分は、来園者はチームで対応します。 管理者が一元的に、Office 365 環境内での来園者の参加を管理し簡単に表示、追加、またはホスト テナントへのゲスト アクセスを無効します。

Teams では常設チャットの機能や通話と会議が利用でき、その強力な拡張性に加えて Office 365 の他のコンポーネントに容易にアクセスできます。  これにより、大企業から小規模な組織にいたるまで、その中にいるすべてのユーザーにとって最適なチームワークのハブを構成します。  

Teams の機能を拡張するために、コネクタ、タブ、およびボットを[アプリ](https://go.microsoft.com/fwlink/?linkid=854629)として利用できます。これらによって、外部の情報、コンテンツ、およびインテリジェントなボットとの対話が Teams にもたらされます。  

<a name="microsoft-teams-infrastructure"></a>Microsoft Teams のインフラストラクチャ
------------------------------

Teams は、Office 365 グループによって作られた既存の Microsoft テクノロジーを基にしています。 Microsoft のクラウドによって、組織はそのコラボレーションの一部として Microsoft Teams を利用する際に優れたパフォーマンスと信頼性を期待することができます。

革新的な発想により、Teams で作成されたチームは、Office 365 グループ、(ドキュメント ライブラリを備えた) SharePoint Online サイト、Teams によって会議の招待などの情報を保存するために使用される Exchange Online グループ メールボックスを作成します。 チームは既存の Office 365 グループを使用して作成でき、既存のグループ メンバーシップと、SharePoint Online および Exchange Online に保存されたコンテンツを Teams に移行することが可能になります。

非公式なリアルタイムの会話を行う場所、永続的なチャットの掲示板のチームも、チームの機能を補完するために、通話や会議、次世代クラウド ・ ベースのインフラストラクチャも Skype の Skype を使用する上に構築された経験を提供します。ビジネスです。 これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。

Office 365 グループは Azure Active Directory (Azure AD) に保存された ID を利用するため、多要素認証 (MFA) のサポートなどの Azure AD におけるすべての認証および承認機能は、Teams ですぐに使用できます。

> [!NOTE]
> 顧客からのフィードバックに基づいて、マイクロソフトのチームでチームの作成の結果として生成された新しい Office 365 のグループされなく Outlook でデフォルトで表示されます。 Outlook でこれらのグループを示すは、既存の動作を継続するお客様の場合は、Outlook の環境のグループを有効にすることができる Exchange のオンラインの PowerShell コマンドレットが提供されます。 Outlook で作成し、後で有効になっているチームのグループは、Outlook とチームの両方に表示する続けます。 この更新プログラムを段階的には数か月の後で Outlook とチーム全体がロールバックされます。


<a name="microsoft-teams-and-office-365"></a>Microsoft Teams と Office 365
------------------------------

それぞれのグループにおいて、機能的な役割やワークスタイルに基づくさまざまなニーズが生じています。 Office 365 は、あらゆるグループの固有のワークスタイルに対応するよう設計されており、次のような専用の統合アプリケーションを提供します。

-   エンタープライズグレードの電子メールに対応した Outlook。現在はグループ機能を備えています。

-   サイトおよびポータル用 SharePoint、インテリジェント コンテンツ サービス、ビジネス プロセスの自動化とエンタープライズ検索。

-   会社規模の接続を推進する Yammer

-   エンタープライズ VoIP およびビデオの法人顧客向けバックボーンとしての Skype for Business。

-   現在は、Office 365 の新しいチャットベースのワークスペースである Microsoft Teams。

Office 365 の各アプリケーションの一般的な使用例を示します。詳細な使用方法については、[FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630) にアクセスしてください。

![Microsoft Teams アイコン。](media/Overview_of_Microsoft_Teams_image1.png)

-   同じグループのメンバーとのリアルタイムでのコラボレーションを望んでいるユーザーおよびチームにより利用されます。

-   プロジェクトに関する迅速な反復を行いながら、ファイルを共有し、共有された成果物に関してコラボレーションを行うことを望んでいるチームをサポートします。

-   プランナー、電源の BI、GitHub など) などのワークスペースにさまざまなツールを接続することができます。

![Microsoft Outlook アイコン。](media/Overview_of_Microsoft_Teams_image2.png)

-   使い慣れた電子メール環境や、より丁寧で真面目な方法で、共同作業を行うことを希望するユーザーにより利用されます。

-   電子メールの使用が必要な固有のビジネス プロセスを提供して、組織の内外の文書や情報を伝達します。

-   周辺のワークグループまたは組織の外側にいるユーザーと通信したり接続します。

![Yammer アイコン。](media/Overview_of_Microsoft_Teams_image3.png)

-   組織全体のユーザーと接続して、プラクティスのコミュニティを中心にまとまり、ベスト プラクティスを共有することをサポートするために利用されます。

-   オープンで透明性の高いフィードベースのプラットフォームを通じて、部門連係ワークフローを改善します

-   リーダーとより広範な従業員ベースの間の双方向の会話により、幹部従業員のエンゲージメントを促進します

-   第一線の労働力を鼓舞して、知識と専門性を共有、享受します

![Skype for Business アイコン。](media/Overview_of_Microsoft_Teams_image4.png)

-   お客様/パートナーとの内部および外部向けのリアルタイムの通信、コラボレーションに利用されます。

-   オーディオ、ビデオ、および大小のチーム (最大 10,000 人の参加者を収容する市役所など) を含むコンテンツを伴う会議を提供します。

-   法人向けのテレフォニー機能を提供します。


![Microsoft SharePoint アイコン。](media/Overview_of_Microsoft_Teams_image5.png)

-   サイトおよびポータル (会社ニュースとお知らせ、検索、およびドキュメントのコラボレーションなど) で利用されます。

-   Microsoft Flow と PowerApps を統合することで、ドキュメント ライブラリと情報のリストに対してビジネス プロセスの自動化を実装します。

-   ファイルの保存、チームのニュース、ページ、リストなどに関して、すべての Microsoft Team に対して自動的にプロビジョニングされる強力な SharePoint チームサイト。

-   [Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)をご覧ください。

## <a name="teams-known-issuesknown-issuesmd"></a>[Teams の既知の問題](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[Teams クライアントのリリース ノート](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a>Teams 管理者のよくあるご質問 (FAQ) はどうなりましたか?

Teams 管理者のよくあるご質問 (FAQ) は、最初に Teams をリリースした時点では便利でしたが、次第に「散らかった引き出し」のような状態になり、特定の情報を見つけ出すのが難しくなってしまいました。 このため、よくあるご質問 (FAQ) は廃止して、お客様が現在参照されているこの Teams のドキュメンテーションに FAQ に関する有益な情報を統合しました。 よくあるご質問 (FAQ) に記載されていた情報はコンテキストに応じてこのドキュメンテーションですべて見つかります。

見つからない場合は、ここのものを探す場合についてお聞かせください、後述の「**フィードバック**」のです。 私たちは、24 時間以内の回答をお送りしてみます。

なお、[Skype for Business から Teams への移行](FAQ-journey.md)に関するよくあるご質問 (FAQ) **は**現在もご利用いただけます。 
