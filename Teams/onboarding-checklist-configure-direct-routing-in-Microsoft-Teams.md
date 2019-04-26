---
title: Microsoft Teams でダイレクト ルーティングを構成するための使用開始チェックリスト
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: チームに直接ルーティングを構成する場合、コア、to do のタスクと活動このチェックリストに従います。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd5badad4051072ff9a52a013f5701501ed8744d
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304766"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>マイクロソフトのチームに直接ルーティングを構成します。

## <a name="direct-routing"></a>ダイレクト ルーティング

| いいえ | 活動またはタスク | 説明 | 完了状態 | その他の情報 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|どの PSTN への接続を展開する組織の場所の決定します。|マイクロソフトでは、Office 365 の電話システムを使用してユーザーに PSTN 接続を提供する別の方法を提供します。<ul><li>システムの計画 (「通話プラン」) を呼び出す場合と電話: Skype オンライン ビジネスとチームの<li>チームにのみ直接ルーティング (「ダイレクト ルーティング」) システムに電話します。<li>システム設置と PSTN への接続に電話: Skype のビジネス オンラインのみ<li>ビジネス クラウド コネクタ ・ エディションの Skype: ビジネス用の Skype オンラインのみ</ul>直接ルーティングにより、組織、計画を呼び出すと同様の利点が、マイクロソフトではなく、サード パーティ プロバイダーが PSTN への接続が容易にします。 展開プランを呼び出すことは、国、または既存の PSTN サービス プロバイダーの契約を維持する必要があるか、特定の設置型システムとの相互運用性が必要な展開で可能になります。<br><br>組織に最も適したどのオプションを決定します。 | |[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[オーディオ会議や予定を呼び出すための契約時のチェックリスト](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|2|ユーザーと直接ルーティングを有効にする展開のリズムの一覧を確認します。|チームに直接ルーティングするためのスコープ内のビジネス単位またはサイトのリストがあることを確認してください。 目標と主要な結果のモデルを使用して、機能を直接ルーティングするためのスコープ内でユーザーになります。 リソースを集中することができますので、サイトごとに操作することをお勧めします。<br><br>対応計画の一環として、特定のユーザーを有効にします、場合によって (パイロット、サイト 1、サイト 2 など)。||[ルーティングの構想を指示します。](2-envision-make-my-service-decisions-direct-routing.md)|
|3|計画し、ライセンスを取得|直接ルーティングのユーザーには、次のライセンスの Office 365 に割り当てられている必要があります。<ul><li>Skype ビジネス オンライン (プラン 2)<li>マイクロソフトの電話システム<li>Microsoft Teams<li>Microsoft オーディオ会議</ul>直接ルーティングに計画を呼び出すことが許可されているユーザーもサポートしています。 計画を呼び出すと、電話システムは、直接ルーティング インターフェイスを使用していくつかの呼び出しをルーティングできます。<br><br>オーディオ会議のライセンスにダイヤルアウトするか、ダイヤルイン番号を提供することによって、スケジュールされたミーティングの場合は、外部の参加者を追加する必要があります。||[ルーティングのライセンスを送る](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4|セッション ボーダー コント ローラー (SBC) のドメイン名の計画します。|SBC ドメイン名は、テナントの「ドメイン」に登録された名前のいずれかをする必要があります。<br><br>**注:** 使用することはできません *. onmicrosoft.com、SBC の完全修飾ドメイン名 (FQDN) にします。<br><br>SBC ドメイン名は、各 SBC に必要な証明書の計画で重要なもあります。||[SBC ドメイン名](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|5|証明書の計画|証明書署名要求 (CSR) を生成することで、SBC の証明書を要求することを強くお勧めします。<br><br>証明書には、[件名]、[共通名、または [サブジェクト代替名フィールドに SBC の FQDN が必要です。 または、直接ルーティングの場合と、共通名またはサブジェクト代替名にワイルドカードをサポートします。<br><br>SBC の CSR を生成する具体的な方法については、SBC の製造元によって提供されるマニュアルを参照してください。<br><br>**追加の情報**列内のアーティクルには、サポートされているルート証明機関が一覧表示されます。||[SBC の信頼された証明書の公開](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|6|計画およびファイアウォールのポートを構成します。|直接ルーティングするための接続ポイントは、次の 3 つの Fqdn です。<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>ポイントを接続し、SBCs の間のトラフィックは、企業のファイアウォールで許可されていなければなりません。 SBC を構成する場合、SBC の TCP ポートを定義します。<br><br>メディア トラフィックは、UDP では。 この種のトラフィックは、メディア ・ プロセッサ ・ コンポーネントとの間をフローします。 SBCs とメディア プロセッサとの間の双方向のトラフィックが、ファイアウォールにもできる必要があります。<br><br>**注:** メディア プロセッサがある動的な IP アドレス、および静的 IP アドレスが表示されます後。 の[Azure データ センターの IP の範囲](https://www.microsoft.com/download/details.aspx?id=41653)に記載されている任意の IP アドレスを許可することが重要です。||[SIP シグナル: Fqdn およびファイアウォールのポート](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[メディア トラフィック: IP アドレスとポートの範囲](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure データ センターの IP の範囲](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|SBCs を構成します。|マイクロソフトでは、直接ルーティングとペアにする認定の SBCs のみサポートします。<br><br>SBCs を構成するには、**追加の情報**列の記事、ベンダー固有のガイダンスと手順を使用します。||[セッション ボーダー コント ローラー (SBCs) のサポート](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|8|直接ルーティングのペアの SBCs|直接ルーティングでは、自分のトランクを使用してダイヤル トーンと PSTN の呼び出し元の機能を提供する各サイトの SBCs を組み合わせる必要があります。<br><br>その特定のサイトの SBC の検証は既にと共に直接ルーティングまたはペアを構成する前に実行しない場合。<br><br>マイクロソフトでは、のみ、認定された SBC の対に直接ルーティングをサポートします。 検証サイトの SBC を認定します。||[電話システムのルーティング サービスを指示する SBC をペアします。](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|9|SBC のペアを検証します。|実行、`Get-CsOnlinePSTNGateway`各 SBC の特定のサイト用にペア化し、パラメーターを**有効**に**は True**の値が表示されることを確認するためのコマンドレットです。<br><br>SBC を取得することを確認するのには、SBC の管理インターフェイスを使用して**200 [OK]** 送信 SIP オプションに対応します。|||
|10|ユーザーの構成を検証します。|ユーザー アカウントが Office 365 で直接作成またはディレクトリ同期を使用して、Office 365 に同期させることを確認します。<br><br>ユーザーに必要なライセンスが割り当てられていることを確認します。<br><br>直接ルーティングは、PSTN の接続のユーザーする必要があります Skype でのオンライン ビジネスのホームは、マイクロソフトのチームに対して有効になっています。||[直接ルーティング サービスのユーザーを有効にします。](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|11|ユーザーの電話番号を構成します。|直接ルーティングするためのスコープ内にあるすべてのユーザーには、自分の電話番号とボイスメールを割り当てる必要があります。<br><br> 使用`Set-CsUser`コマンドレットには、ボイスメールを有効にして、ユーザーに電話番号を割り当てます。||[電話番号を構成し、エンタープライズ ボイスとボイス メールを有効にします。](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|12|音声ルーティングを構成します。|電話システムに基づく特定の SBC に送られる呼び出しを可能にするためのルーティング メカニズムがあります。<ul><li>番号のパターンと呼ばれる<li>番号のパターン + 呼び出しでは、特定のユーザーと呼ばれます。</ul>音声が作成することによって、ユーザーのルーティングを構成します。<ul><li>音声ルーティング ポリシー<li>PSTN の使用法<li>ボイス ルート<li>オンラインの PSTN ゲートウェイ</ul>||[音声ルーティングを構成します。](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|13|ユーザー優先の呼び出し元のクライアントとして Microsoft チームの設定します。|マイクロソフトのチームでは、[**通話**] タブを表示することができます、前に、マイクロソフトのチームでのテナントの**プライベート通話**を有効にする必要がありを**優先クライアントを呼び出すこと**、ユーザーのチームのクライアントを構成する必要があります。||[マイクロソフト チームの呼び出しを有効にします。](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[ユーザー優先の呼び出し元のクライアントとして Microsoft チームの設定します。](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|14|直接ルーティングのユーザーを有効にします。|音声ルーティング ポリシーを構成済みの SBC を直接ルーティングを使用して、PSTN の呼び出しを取得し、ユーザーに割り当てます。||[直接ルーティング サービスのユーザーを有効にします。](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|15|準備し、ユーザー受け入れテストを実行します。|準備し、ダイヤルインとダイヤルアウトのシナリオを含む、ユーザー受け入れテストを実行します。||[チームでクラウド音声の作業負荷をテスト](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|16|レポートの利用状況、状態、重要な成功指標 (KSIs)、および品質|Envision フェーズ中に定義したとおり、使用状況、健康、KSIs、および品質を報告します。||[運用ガイド](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>次のステップ

このチェックリストを完了するが正常に構成した直接ルーティング チーム展開を。

次の手順では、 [(戦略) の音声をサイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用してユーザーを支援するオンボードの各サイトと計画し、重要なサイト固有のアクティビティを実行することを防止します。
