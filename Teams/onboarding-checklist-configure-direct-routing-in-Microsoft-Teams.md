---
title: Microsoft Teams でダイレクト ルーティングを構成するための使用開始チェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Teams で直接ルーティングを構成する場合は、このチェックリストでコア、to do、タスク、アクティビティに従います。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a69b71c4b55987b9495ebef149e8057fa6340775
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902864"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>Microsoft Teams で直接ルーティングを構成する

## <a name="direct-routing"></a>ダイレクト ルーティング

| いいえ | アクティビティまたはタスク | 説明 | 完了状態 | その他の情報 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|組織の場所に合わせて展開する PSTN 接続を決定する|Microsoft は、Office 365 Phone システムを使用してユーザーに PSTN 接続を提供するための別の方法を提供しています。<ul><li>通話プラン (「通話プラン」) を搭載した電話システム: Skype for Business Online と Teams<li>電話システムによる直接ルーティング (「ダイレクトルーティング」): Teams のみ<li>オンプレミスの PSTN 接続を備えた電話システム: Skype for Business Online のみ<li>Skype for Business Cloud Connector Edition: Skype for Business Online のみ</ul>直接ルーティングを使用すると、組織は通話プランと同じ利点が得られます。ただし、PSTN 接続は Microsoft ではなくサードパーティプロバイダーによって提供される点が異なります。 これにより、通話プランを利用できない国で展開したり、既存の PSTN サービスプロバイダコントラクトを管理する必要がある、または特定のオンプレミスシステムとの相互運用性が求められる展開での展開が可能になります。<br><br>組織に最適なオプションを特定します。 | |[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[電話会議と通話プランのオンボードチェックリスト](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|2|ダイレクトルーティングを有効にするために、ユーザーの一覧と展開の間隔を確認する|チームとの直接ルーティング用に、ビジネスユニットまたはサイトの一覧が範囲内にあることを確認します。 目標と主要な結果モデルを使用して、直接ルーティングの対象となるユーザーを特定します。 サイトごとに作業することをお勧めします。これにより、リソースに集中することができます。<br><br>有効化計画の一環として、どのユーザーがどのような場合に有効にするか (パイロット、サイト1、サイト2など) を特定します。||[ダイレクトルーティングの構想](2-envision-make-my-service-decisions-direct-routing.md)|
|3|ライセンスの計画と取得|直接ルーティングのユーザーには、Office 365 で次のライセンスが割り当てられている必要があります。<ul><li>Skype for Business Online (プラン 2)<li>Microsoft 電話システム<li>Microsoft Teams<li>Microsoft 電話会議</ul>また、ダイレクトルーティングは、通話プランのライセンスが付与されているユーザーもサポートします。 通話プランを使用する電話システムでは、直接ルーティングインターフェイスを使用して、一部の通話をルーティングできます。<br><br>電話会議ライセンスは、スケジュールされた会議に外部参加者を追加するために必要です。または、ダイヤルイン番号を指定します。||[ダイレクトルーティングライセンス](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4|セッションボーダーコントローラー (SBC) のドメイン名を計画する|SBC ドメイン名は、テナントの "Domains" に登録されている名前のいずれかである必要があります。<br><br>**注:** SBC の完全修飾ドメイン名 (FQDN) に onmicrosoft.com を使用することはできません。<br><br>SBC ドメイン名は、各 SBC に必要な証明書を計画する際にも重要です。||[SBC ドメイン名](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|5|証明書の計画|認定署名要求 (CSR) を生成することで、SBC の証明書を要求することを強くお勧めします。<br><br>証明書は、subject、common name、またはサブジェクトの代替名の各フィールドに SBC FQDN を設定する必要があります。 または、ダイレクトルーティングでは、共通名またはサブジェクト代替名のワイルドカードをサポートしています。<br><br>SBC の CSR を生成するための具体的な手順については、SBC ベンダーから提供されているドキュメントを参照してください。<br><br>[**追加情報**」列の記事では、サポートされているルート証明機関を一覧表示します。||[SBC 用の公開された信頼できる証明書](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|6|ファイアウォールポートの計画と構成|直接ルーティングの接続ポイントは、次の3つの Fqdn です。<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>これらの接続ポイントと SBCs 間のトラフィックは、会社のファイアウォールで許可されている必要があります。 Sbc を構成するときは、SBC の TCP ポートを定義します。<br><br>メディアトラフィックは UDP にあります。 この種類のトラフィックは、メディアプロセッサコンポーネントとの間で送受信されます。 SBCs とメディアプロセッサ間の双方向トラフィックも、ファイアウォールで許可されている必要があります。<br><br>**注:** メディアプロセッサには動的 IP アドレスがあり、静的な IP アドレスは後で利用可能になります。 [Azure Datacenter の Ip 範囲](https://www.microsoft.com/download/details.aspx?id=41653)に記載されている ip アドレスを許可することが重要です。||[SIP シグナリング: Fqdn とファイアウォールのポート](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[メディアトラフィック: IP アドレスとポート範囲](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure Datacenter IP 範囲](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|SBCs を構成する|Microsoft は、認定された SBCs とダイレクトルーティングをサポートしています。<br><br>ベンダー固有のガイダンスと**追加情報**列の記事に記載されている手順を使用して、SBCs を構成します。||[サポートされているセッション境界コントローラー (SBCs)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|個|SBCs とダイレクトルーティングを組み合わせる|各サイトの SBCs は、独自の trunks を使用してダイヤルトーンと PSTN 通話機能を提供するために、ダイレクトルーティングとペアリングされている必要があります。<br><br>特定のサイトの SBC が直接ルーティングとペアリングされていることを検証するか、実行されていない場合はペアを構成します。<br><br>Microsoft は、認定された SBC と直接ルーティングをサポートしています。 そのサイトの SBC が認定されていることを確認します。||[電話システムの SBC to Direct ルーティングサービスをペアリングする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|ファイブ|SBC ペアリングを検証する|特定の`Get-CsOnlinePSTNGateway`サイトとペアリングした SBC ごとにコマンドレットを実行し、**有効な**パラメーターで値**True**が表示されることを確認します。<br><br>Sbc 管理インターフェイスを使用して、SBC が発信 SIP オプションに**200 の "OK"** の応答を取得することを確認します。|||
|常用|ユーザー構成を検証する|ユーザーアカウントが Office 365 で直接作成されているか、ディレクトリ同期を使用して Office 365 に同期されていることを確認します。<br><br>必要なライセンスがユーザーに割り当てられていることを確認します。<br><br>直接ルーティングを使用する PSTN 接続の場合、ユーザーは Skype for Business Online を使って Microsoft Teams を有効にしている必要があります。||[ユーザーのダイレクトルーティングサービスを有効にする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|折り|ユーザーの電話番号を構成する|直接ルーティングする範囲内のすべてのユーザーに、電話番号とボイスメールを割り当てる必要があります。<br><br> コマンド`Set-CsUser`レットを使用してボイスメールを有効にし、電話番号をユーザーに割り当てます。||[電話番号を設定し、エンタープライズボイスとボイスメールを有効にする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|以内|音声ルーティングを構成する|電話システムには、以下に基づいて特定の SBC に通話を送信することができるルーティングメカニズムがあります。<ul><li>"番号パターン" と呼ばれる<li>通話を発信している番号パターンと、特定のユーザー</ul>以下を作成して、ユーザーの音声ルーティングを構成します。<ul><li>音声ルーティングポリシー<li>PSTN の使用状況<li>音声ルート<li>オンライン PSTN ゲートウェイ</ul>||[音声ルーティングを構成する](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|14|ユーザーの優先発信クライアントとして Microsoft Teams を設定する|ユーザーが Microsoft Teams の [**通話**] タブを表示するには、microsoft teams でテナントの**プライベート通話**を有効にする必要があります。また、チームクライアントは、ユーザーの**優先発信クライアント**として構成されている必要があります。||[Microsoft Teams の通話を有効にする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[ユーザーの優先発信クライアントとして Microsoft Teams を設定する](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|14|ユーザーが直接ルーティングできるようにする|構成された SBC 経由で直接ルーティングを使用して、PSTN 通話を発信および取得するユーザーに、音声ルーティングポリシーを割り当てます。||[ユーザーのダイレクトルーティングサービスを有効にする](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|マート|ユーザー受け入れテストを準備して実行する|ダイヤルインやダイヤルアウトのシナリオなど、ユーザー受け入れテストを準備して実行します。||[Teams でクラウドの音声ワークロードをテストする](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|16|使用状況、正常性、キーの成功インジケーター (KSIs)、および品質のレポート|ビジョン化フェーズで定義した使用状況、正常性、KSIs、および品質をレポートします。||[運用ガイド](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>次のステップ

このチェックリストを完了すると、チーム展開との直接ルーティングが正常に構成されます。

次の手順として、お客様が各サイトでの使用を計画し、サイト固有の重要なアクティビティを計画して実行できるように、[音声 (プレイブック) 向けのサイト支援プレイブック](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用します。
