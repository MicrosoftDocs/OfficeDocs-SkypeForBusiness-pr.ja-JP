---
title: オンボーディング チェックリスト - ダイレクト ルーティングを構成する - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teams で直接ルーティングを構成する場合は、このチェックリストの主要な To Do タスクとアクティビティに従います。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 19a196c9a995bf146e2737ff72b298a0be2b3392
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812927"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>Microsoft Teams で直接ルーティングを構成する

## <a name="direct-routing"></a>ダイレクト ルーティング

| いいえ | アクティビティまたはタスク | 説明 | 完了状態 | その他の情報 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|組織の場所に展開する PSTN 接続を決定する|Microsoft は、Microsoft 365 または Office 365 電話システムを使用するユーザーに PSTN 接続を提供する代替方法を提供します。<ul><li>通話プラン付き電話システム ("通話プラン"): Skype for Business Online と Teams<li>電話システムダイレクト ルーティング ("ダイレクト ルーティング"): Teams のみ<li>オンプレミス PSTN 接続を使用した電話システム: Skype for Business Online のみ<li>Skype for Business Cloud Connector エディション: Skype for Business Online のみ</ul>直接ルーティングは、PSTN 接続が Microsoft ではなくサードパーティ プロバイダーによって促進される点を除き、組織に通話プランと同じ利点を提供します。 これにより、通話プランが利用できない国や、既存の PSTN サービス プロバイダー契約を維持する必要がある展開や、特定のオンプレミス システムとの相互運用性が必要な展開での展開が可能になります。<br><br>組織に最も適したオプションを決定します。 | |[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[電話会議と通話プランのオンボーディング チェックリスト](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|2|直接ルーティングを有効にするためのユーザーのリストと展開の更新の更新を確認する|Teams での直接ルーティングの範囲に、ビジネス ユニットまたはサイトの一覧が表示されている必要があります。 目標と主要な結果モデルを使用して、直接ルーティングの対象となるユーザーを確認します。 リソースに集中できるよう、サイト単位で作業することをお勧めします。<br><br>有効化プランの一環として、有効にするユーザーを特定します (パイロット、サイト 1、サイト 2 など)。||[ダイレクト ルーティングの構想](2-envision-make-my-service-decisions-direct-routing.md)|
|3|ライセンスを計画して取得する|直接ルーティングのユーザーには、Microsoft 365 または 365 で次のライセンスOffice必要があります。<ul><li>Skype for Business Online (プラン 2)<li>Microsoft Phone System<li>Microsoft Teams<li>Microsoft 電話会議</ul>ダイレクト ルーティングは、通話プランのライセンスを取得したユーザーもサポートします。 通話プランが設定された電話システムでは、ダイレクト ルーティング インターフェイスを使用して一部の通話をルーティングできます。<br><br>ダイヤルアウトするかダイヤルイン番号を指定して、スケジュールされた会議に外部参加者を追加するには、電話会議ライセンスが必要です。||[ダイレクト ルーティング ライセンス](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4|セッション ボーダー コントローラー (SBC) ドメイン名を計画する|SBC ドメイン名は、テナントの "Domains" に登録されている名前の 1 つである必要があります。<br><br>**注:** SBC の完全修飾ドメインonmicrosoft.com (FQDN) に *.onmicrosoft.com を使用することはできません。<br><br>SBC ドメイン名は、SBC ごとに必要な証明書を計画する場合にも重要です。||[SBC ドメイン名](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|5|証明書の計画|証明書署名要求 (CSR) を生成して、SBC の証明書を要求することを強く推奨します。<br><br>証明書には、件名、共通名、または件名の代替名フィールドに SBC FQDN が含まれています。 または、直接ルーティングでは、共通の名前または件名の代替名のワイルドカードがサポートされます。<br><br>SBC の CSR の生成に関する具体的な手順については、SBC ベンダーが提供するドキュメントを参照してください。<br><br>「追加情報」列 **の記事には** 、サポートされているルート証明機関の一覧が示されています。||[SBC のパブリック信頼済み証明書](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|6|ファイアウォールポートを計画して構成する|ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>これらの接続ポイントと SPC 間のトラフィックは、企業ファイアウォールで許可する必要があります。 SBC を構成する場合は、SBC で TCP ポートを定義します。<br><br>メディア トラフィックは UDP 上です。 この種類のトラフィックは、メディア プロセッサ コンポーネントとメディア プロセッサ コンポーネントの間でフローします。 また、SPC とメディア プロセッサ間の双方向トラフィックもファイアウォールで許可する必要があります。<br><br>**注:** メディア プロセッサは動的 IP アドレスを持ち、静的 IP アドレスは後で使用できます。 Azure データセンターの IP 範囲に記載されている IP アドレスを許可 [することが重要です](https://www.microsoft.com/download/details.aspx?id=41653)。||[SIP シグナリング: FQDN とファイアウォール ポート](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[メディア トラフィック: IP アドレスとポート範囲](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure データセンターの IP 範囲](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|SBC を構成する|Microsoft は、認定された SPC のみをサポートし、ダイレクト ルーティングとペアリングします。<br><br>ベンダー固有のガイダンスと「追加情報」列の記事の手順を使用して、SPC **を構成** します。||[サポートされているセッション ボーダー コントローラー (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|8|直接ルーティングを使用して SPC をペアリングする|独自のトランクを使用してダイヤル トーンと PSTN 通話機能を提供するには、各サイトの SPC をダイレクト ルーティングとペアリングする必要があります。<br><br>特定のサイトの SBC が直接ルーティングと既にペアリングされているのを検証するか、前に実行されていない場合はペアを構成します。<br><br>Microsoft は、認定された SBC のみをサポートし、ダイレクト ルーティングとペアリングします。 そのサイトの SBC が認定を受けたか検証します。||[電話システムのダイレクト ルーティング サービスに SBC をペアリングする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|9|SBC のペアリングを検証する|特定のサイトに対してペアリングした SBC ごとにコマンドレットを実行し、[有効] パラメーターに値 `Get-CsOnlinePSTNGateway` **True** が表示されるのを確認 **します**。<br><br>SBC 管理インターフェイスを使用して、SBC が送信 SIP オプションに対して **200 の "OK"**  応答を受け取るのを確認します。|||
|10|ユーザー構成を検証する|ディレクトリ同期を使用して、ユーザー アカウントが Microsoft 365 または Office 365 に直接作成または同期されるのを確認します。<br><br>必要なライセンスがユーザーに割り当てられているか確認します。<br><br>直接ルーティングを使用する PSTN 接続の場合、ユーザーは Skype for Business Online に自宅にいて、Microsoft Teams で有効になっている必要があります。||[ダイレクト ルーティング サービスのユーザーを有効にする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|11|ユーザーの電話番号を構成する|ダイレクト ルーティングの対象に入っているすべてのユーザーには、電話番号とボイスメールが割り当てられている必要があります。<br><br> コマンドレット `Set-CsUser` を使用してボイスメールを有効にし、ユーザーに電話番号を割り当てる。||[電話番号を構成し、エンタープライズボイスメールとボイスメールを有効にする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|12|音声ルーティングを構成する|電話システムには、通話を次に基づいて特定の SBC に送信できるルーティング メカニズムがあります。<ul><li>呼び出される番号パターン<li>呼び出される番号パターン + 通話を行う特定のユーザー</ul>次を作成して、ユーザーの音声ルーティングを構成します。<ul><li>音声ルーティング ポリシー<li>PSTN 使用状況<li>音声ルート<li>オンライン PSTN ゲートウェイ</ul>||[音声ルーティングを構成する](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|13|Microsoft Teams をユーザーの優先呼び出しクライアントとして設定する|ユーザーが Microsoft Teamsの [通話] タブを表示するには、Microsoft Teams でテナントのプライベート通話を有効にする必要があります。Teams クライアントをユーザーの優先呼び出しクライアントとして構成する必要があります。 ||[Microsoft Teams の通話を有効にする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[Microsoft Teams をユーザーの優先呼び出しクライアントとして設定する](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|14|ユーザーに直接ルーティングを有効にする|構成された SBC を通じて直接ルーティングを使用して PSTN 通話を発信および受信するユーザーに音声ルーティング ポリシーを割り当てる。||[ダイレクト ルーティング サービスのユーザーを有効にする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|15|ユーザー受け入れテストを準備して実行する|ダイヤルインとダイヤルアウトのシナリオを含む、ユーザー受け入れテストを準備して実行します。||[Teams でクラウド音声ワークロードをテストする](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|16|使用状況、正常性、主要成功インジケーター (KSIs)、品質を報告する|ビジョン フェーズで定義した使用状況、正常性、KSIs、品質について報告します。||[運用ガイド](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>次の手順

このチェックリストを完了すると、Teams の展開で直接ルーティングが正常に構成されます。

次の手順として、音声用サイト有効化プレイブック [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用して、各サイトでユーザーをオンボードし、サイト固有の重要なアクティビティを計画して実行するのに役立ちます。
