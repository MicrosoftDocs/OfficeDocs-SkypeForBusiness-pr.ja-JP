---
title: Teams の連絡先センター
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: Microsoft Teams のサービス (CCaaS) ソリューションとしての統合された連絡先センターの概要
appliesto:
- Microsoft Teams
ms.openlocfilehash: 651cacb23aaa390a946bad985c64752f9035ac6f
ms.sourcegitcommit: ec4280f6b02bea9616bf4d799cd81ff87f17588f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292241"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Microsoft Teams の連絡先センターの統合

人気のある連絡先センターのソリューションを Microsoft Teams と統合することは、チームの通話機能を展開するユーザーにとって一般的なニーズです。  この記事では、microsoft teams との連絡先センターソリューションの統合方法の概要について説明します。また、Microsoft Teams が接続された連絡先センター認定プログラムに参加しているパートナーソリューションの追加情報についても説明します。

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>Microsoft Teams の連絡先センターの統合について教えてください。

今日の連絡先センターでは、サポートが大幅にサポートされています。この機能は、お客様のブランドを使用したお客様の経験に基づく、操作やフィルター処理を行う主要な車両の1つとして機能します。 今日のお客様は、世界中どこでも、電話、メール、テキスト、ソーシャルなどの広範なチャネルを使用することを希望しています。また、現在の日付の購入プロセスに関連付けられている一連の連絡量が多いため、多くの組織が、次の2つのことを実現しています。

1. 組織内のすべてのメンバーが、お客様に直接対応するために関与する可能性があります。そのため、適切なツールを用意する必要があります。

2. このようにユーザー操作の範囲を拡大すると、一貫性、継続的な改善、拡大縮小を支援するツールが必要になります。

Microsoft Teams では、チャット、ビデオ会議、通話などの通信モードを通じて、内部および外部顧客との接続のハブとして機能することによって、顧客対話型の作業ストリームをサポートしています。 Microsoft Teams の[クラウド音声機能](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)([自動応答](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants)、[通話キュー](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)など) については、それぞれのニーズに合わせて機能と構成を提供します。

ビジネスツールとワークフローを使用して顧客とのやり取りを促進する統合ソリューションを望む他のお客様には、Microsoft Teams も、業界の主要な連絡先センターの一部として、サービス (CCaaS) ソリューションプロバイダーと統合されています。

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Microsoft Teams 認定プログラム用の接続された連絡先センター

公開されている利用可能な Api を公開して、パートナーが CCaaS をチーム向けのソリューションとして開発し、統合できるようにしました。 Microsoft Teams 認定プログラム用の接続された連絡先センターが開発され、お客様は Microsoft のソリューションで期待される品質、互換性、および信頼性を確保することができます

次のパートナーは、Microsoft Teams のソリューションを認定するためのプロセスを担当しています。

| **パートナー**                                                                                                                              | **ソリューションの web サイト**                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Anywhere365 | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| ComputerTalk | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| Enghouse Interactive | https://enghouseinteractive.co.uk/microsoft/                                                       |
| Five9 | https://www.five9.com/products/application-integration/uc-integration                                                   |
| Genesys | https://www.genesys.com/microsoft                                                                                   |
| Luware | https://luware.com/en/solutions/                                                                                       |
| 便利な連絡先 | https://www.niceincontact.com/microsoft-teams                                                            |

このリストは、パートナーが参加して認定条件を満たしたときに更新されます。

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>Microsoft Teams での連絡先センターソリューションの動作方法を教えてください。

Microsoft Teams には、次のようなサードパーティのボイスソリューションの開発をサポートするさまざまな機能が用意されています。

1. [直接ルーティング接続](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [Microsoft Graph Cloud Communication Api](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Teams のプラットフォームと拡張性

4. Teams Sdk

これらの機能を組み合わせると、次の3つの統合モデルが実現します。

  - **接続**(直接ルーティング経由)

  - **接続と拡張**(直接ルーティング、Graph Api、Teams アプリプラットフォーム)

  - **拡張とパワー**の適用 (ネイティブチームとの対話用の3P アプリへの teams sdk の埋め込み)

### <a name="connect"></a>接続

このモデルでは、Microsoft Teams 電話システムインフラストラクチャを使用して CCaaS パートナーに接続し、強化されたルーティング、構成、システムの分析機能を有効にします。 このモデルでは、連絡先センターパートナーソリューションは、選択した番号とユーザーに対してテレフォニーサービスを提供することもできます。

Connect モデルに構築されたソリューションを使用するエージェントは、情報 & 洞察を収集することができます。また、必要に応じて、チームで SME のプレゼンスを活用して、可用性を確保することもできます。

組織では、自動化された仮想アシスタントとスキルベースのルーティングキューを設定することによって、最適なエージェントへの通話を確実に行うことができます。

**機能のハイライト:**

次に示すのは、この統合モデルの機能に関する包括的な一覧ではありませんが、フォーカス領域には次のものが含まれます。

  - Office 365 authN を使用すると、エージェントは、統合された CCaaS クライアントから Microsoft テナントに接続することができます。 

  - Teams ユーザーからのプレゼンス表示 

  - 直接ルーティングを使用した通話フロー (テストプランで示されています) 

  - Teams ユーザーとの転送とグループ通話のサポート 

  - Teams との統合のための teams Graph Api とクラウド通信 Api 

  - 複数のお客様をパートナーの SBC でサポートするために、マルチテナント SIP トランクをサポートできるようにします。  

  - [ <span class="underline">Microsoft 認定セッションボーダーコントローラー (SBC)</span>を実装するパートナー](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>接続と拡張

このモデルでは、team [client platform](https://docs.microsoft.com/microsoftteams/platform/overview)、Teams [Graph Api](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 、および[MICROSOFT Graph の Cloud Communications Api](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)を使用して teams クライアントと統合し、コンタクトセンターのユーザーとエージェントの操作を拡張します。このモデルでは、すべての連絡先センターの通話と通話コントロールエクスペリエンスに teams 電話システムを使用しています。 このモデルでは、連絡先センターパートナーは、Microsoft 365 と共にテレフォニーキャリアとして機能します。

Connect と拡張ベースのソリューションを活用することで、エージェントは、契約を開始する前に複数のシステムのデータを関連付けて、内部のコラボレーションと外部通信の両方について、チーム内でネイティブに作業することによって、コストの高いコンテキスト切り替えを回避することができます。

組織では、個人に向けてワークフローと高度なルーティング構成を設計することで、システムとやり取りの品質を測定することができます。

**機能のハイライト:**

次の例は、この統合モデルの機能機能の包括的な一覧ではありませんが、主要なフォーカス領域を強調しています。

  - Teams との統合のための teams Graph Api とクラウド通信 Api 

  - エージェントエクスペリエンス用の Teams ベースのアプリ 

  - エージェントのプライマリ通話エンドポイントとしてのチーム 

  - すべての通話コントロールを対象としたチームクライアントの呼び出し

  - エージェントエクスペリエンスアプリは、Teams web とモバイルクライアントでも作業できるようにする必要があります。

  - チーム内の CCaaS アプリ内のエージェントに対する分析、ワークフロー管理、役割ベースのエクスペリエンス

  - チームクライアントと統合されたチャットとコラボレーションのエクスペリエンス 

  - すべてのアプリでのチームクライアントエクスペリエンスのパフォーマンスと品質の維持  

### <a name="extend-and-power"></a>延長とパワー

このモデルを使用すると、パートナーはネイティブの Azure ベースのボイスアプリケーションを作成できます。これにより、チーム呼び出しインフラストラクチャとクライアントプラットフォームを活用して、コラボレーティブな顧客とエージェント接続の先進のインテリジェントソリューションを提供できます。 拡張とパワーの目標は、開発者の創造性を stoke、顧客の生産性を向上させることです。

Azure で直接構築することにより、パートナーは、benefitting のストレージ、コンピューティング、分析 & 認知サービスを利用しながら、すべてのチームの地域と地域、および共有されたグローバル通信ネットワークからソリューションを迅速に展開し、プロビジョニングすることができます。

拡張およびパワー統合モデルを使用することで、パートナーは、チャネル間通信のエクスペリエンスを提供しながら、参加者や他のサービスをどのように使用するかをカスタマイズすることができます。これには、[クラウド通信 API](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)を活用しています。

**機能のハイライト:**

次に示すのは、この統合モデルの機能機能の包括的な一覧ではありませんが、接続モデルと拡張モデルによって提供される領域に加えて、これらの領域を強調表示しています。

  - Teams SDK を使用した、正式なエージェントによる方向性チャネル通信のネイティブ有効化 

  - チームコラボレーションサービスを活用して、エージェントのコラボレーションと顧客のやり取りを実現する  

  - クラウドサービスの迅速なプロビジョニング、どこからでも展開 

  - チームでの会話中にユーザーと直接会話を制御し、対話する 

### <a name="comparing-connected-contact-center-integration-models"></a>接続されている連絡先センターの統合モデルの比較

Microsoft Teams でサポートされている統合モデルの概要については、以下の表を参照してください。

<table>
<thead>
<tr class="header">
<th></th>
<th><strong>Teams の音声アプリ</strong></th>
<th><strong>接続</strong></th>
<th><strong>Connect + extend</strong></th>
<th><strong>Extend + power</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>クラウドサービスモデル</td>
<td>Microsoft</td>
<td>パートナー</td>
<td><p>パートナー +</p>
<p>Microsoft</p></td>
<td>Microsoft</td>
</tr>
<tr class="even">
<td>誰がこのソリューションを運営していますか?</td>
<td>Microsoft</td>
<td>パートナー</td>
<td>パートナー</td>
<td>パートナー</td>
</tr>
<tr class="odd">
<td>M365 サインイン</td>
<td>はい</td>
<td>はい</td>
<td>はい</td>
<td>はい</td>
</tr>
<tr class="even">
<td>チームと通話しているユーザー</td>
<td>非公式、SME</td>
<td>非公式、SME</td>
<td>非公式、SME、正式 *</td>
<td>非公式、SME、フォーマル</td>
</tr>
<tr class="odd">
<td>IW/SME の体験</td>
<td>Teams</td>
<td>Teams</td>
<td><p>Teams +</p>
<p>extensions</p></td>
<td><p>Teams +</p>
<p>extensions</p></td>
</tr>
<tr class="even">
<td>サービス接続</td>
<td>プラットフォーム<br />
(通話プラン + DR)</td>
<td>直接ルーティング</td>
<td>直接ルーティング</td>
<td>プラットフォーム<br />
(通話プラン + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>次の手順

認定プログラムへの参加を求めるベンダーの場合は、メールでお問い合わせください <Teamscategorypartner@microsoft.com> 。
