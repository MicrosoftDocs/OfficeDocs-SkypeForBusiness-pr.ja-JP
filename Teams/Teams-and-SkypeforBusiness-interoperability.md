---
title: "Microsoft Teams と Skype for Business の相互運用性"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Teams と Skype for Business の相互運用性とそれがチャットや通話のエクスペリエンスに及ぼす影響について説明します。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08954783a3e0aaf8ae6b54c621ea21c67df6208e
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
<a name="microsoft-teams-and-skype-for-business-interoperability"></a>Microsoft Teams と Skype for Business の相互運用性
=======================================================

Skype for Business を使用している組織で Teams の使用開始を検討している場合は、これら 2 つのアプリケーションの相互運用性を設定する方法を理解することが重要です。

> [!IMPORTANT]
> このドキュメントでは、Teams での通話プランのサポートについて初期段階の評価を行います。 Teams の相互運用性のポリシーに関する詳細は将来的に変更される予定です。

Skype for Business や Teams の相互運用性により、組織全体で流動的な通信が実現し、ユーザーはお互いにチャットや通話を行うことができます。 Microsoft は、IT 専門家が Teams の導入を管理できるよう支援するための新しい Teams 相互運用性ポリシーを追加しています。このポリシーは [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) コマンドレットを使用して Skype for Business の Windows PowerShell リモート セッションを開いて管理できます。 このポリシーを使用して、組織で必要とされる機能性を実現するよう Teams を設定します。


> [!TIP]
> 相互運用性を実現するために必要な PowerShell コマンドレットを検索するには、[Skype for Business PowerShell のコマンドレットに関するドキュメント](https://docs.microsoft.com/powershell/module/skype) で [**フィルター**] ボックスに「CsTeamsInteropPolicy」と入力します。

Teams の相互運用性ポリシーを使用することで、IT 専門家はユーザーがチャットや通話の受信に優先的に使用するアプリケーションを指定することができます。 相互運用性ポリシーでは Teams と Skype for Business で縦割り的に通信を処理するか、ユーザーがアプリケーションの枠組みを超えて通信できるように設定することができます。

Teams の相互運用ポリシーはテナント レベルまたはユーザー レベルで定義できます。さらに、チャットや通話を受信するために使用するアプリケーションをユーザーが選択できるように設定することもできます。

この固有の柔軟性により、組織は最適なペースと方法で Teams の試行、評価、および Teams への移行を実施することができます。

> [!NOTE]
> Teams と Skype for Business の相互運用性は、純粋にオンラインの構成 (Skype for Business Online と Teams) を利用するユーザー間、および混在 (ハイブリッド) 展開のトポロジにおいて Skype for Business オンプレミス展開で所属しているユーザー間でサポートされます。

## <a name="what-interoperability-means"></a>相互運用性とは
相互運用性とは、Teams と Skype for Business のユーザーが Teams と Skype for Business 間でチャット (IM) や通話をやり取りするための機能です。

Skype for Business から Teams への移行を開始した組織では、異なるクライアントを利用しているユーザーが混在することが考えられます。

Teams では、生産性を維持するため、使用するアプリケーション (Teams または Skype for Business) に関係なくユーザーがお互いに通信できるようにする機能が提供されています。

サポートされる相互運用のエクスペリエンスを次に示します。
- Teams を使用していない Skype for Business ユーザーが Teams ユーザーとチャットすることができます (その逆も可)<p>
![Teams からの相互運用チャットのエクスペリエンス](media/Interop_chat_experience_from_Teams.png)<br>
- Skype for Business ユーザーは Teams ユーザーに対して音声通話やビデオ通話を行うことができます (その逆も可)。 相互運用での通話でも、通話の転送などの詳細な通話オプションはこれまでどおり利用できます。<p>
![Teams からの相互運用の通話のエクスペリエンス](media/Interop_calling_experience_from_Teams.png)<br>

> [!NOTE]
> Skype for Business ユーザー側からの視点では、Teams に対するチャットや通話のやり取りは Skype for Business の基本的なチャットや通話と同じように表示されます。 詳しくは、「[相互運用のエクスペリエンスの制限](#interop-experiences-limitations)」セクションをご覧ください。

> [!IMPORTANT]
> Teams と Skype for Business 間における統一された表示形式は現在サポートされていません。Teams と Skype for Business ではそれぞれに固有の表示形式が使用されます。 統一された表示形式のサポートが利用可能になる時期については、「[Skype for Business から Microsoft Teams へ: 機能のロードマップ](https://aka.ms/skype2teamsroadmap)」をご覧ください。

## <a name="interop-requirements"></a>相互運用の要件
相互運用の機能を有効にするには、ユーザーが次の条件を満たしている必要があります。
- ユーザーに対して Teams を有効にする (ライセンスを割り当てる) 必要があります
- ユーザーに対して Skype for Business Online を有効にする (ライセンスを割り当てる) 必要があります
    - この要件は、Teams のみを使用する予定のユーザーまたは Teams を主なチャット/通話アプリケーションとして使用するユーザーに適用されます
- ハイブリッドの Skype for Business 展開の場合
    - オンプレミスの Skype for Business (または Skype for Business ハイブリッド展開で現在サポートされている Lync Server バージョン) に所属しているユーザーは、Teams を使用しているクラウド ユーザーと相互運用できます
    - Teams を主なチャット/通話アプリケーションとして使用する予定のクラウド ユーザーに対して Skype for Business Online を有効にする (ライセンスを割り当てる) 必要があります

## <a name="supported-topologies-for-interop"></a>相互運用でサポートされるトポロジ
Teams と Skype for Business の相互運用は主に次の Skype for Business 展開トポロジでサポートされます。
- Skype for Business Online のみ
- Skype for Business ハイブリッド (Skype for Business Online と Skype for Business オンプレミスが混在する展開)

### <a name="skype-for-business-online-only-topology"></a>Skype for Business Online のみのトポロジ
Skype for Business Online 展開のみを実施している組織では、Skype for Business Online ユーザーと Teams ユーザー間でチャットや通話の相互運用を確立することができます。

このトポロジでは、相互運用を機能させるには、Teams を主なチャット/通話アプリケーションとして設定しているユーザーに対して Skype for Business Online も有効にする必要があります。

![Skype for Business Online のみの展開トポロジにおける相互運用](media/Interop_SkypeforBusinessOnlineOnly_topology.png)

### <a name="skype-for-business-hybrid-deployment-topology"></a>Skype for Business ハイブリッド展開トポロジ
ハイブリッド展開トポロジにおいて Skype for Business Online と Skype for Business サーバー (オンプレミス) が混在する展開を実施している組織では、Skype for Business ユーザー (オンラインまたはオンプレミスのいずれかのユーザー) と Teams ユーザー間でチャットや通話の相互運用を実現することができます。

Skype for Business Online のみの展開トポロジと同様に、相互運用を機能させるには、Teams を主なチャット/通話アプリケーションとして設定しているユーザーに対して Skype for Business Online も有効にし、それに所属するよう設定する必要があります。

![Skype for Business ハイブリッド展開トポロジにおける相互運用](media/Interop_SkypeforBusinessHybrid_topology.png)

> [!IMPORTANT]
> Skype for Business ハイブリッドの相互運用のサポートには、CCE (Cloud Connector エディション) または一般的に OPCH (On Prem Config Hybrid) と呼ばれる既存の展開を使用するオンプレミス PSTN 接続性によって提供される Hybrid Voice 機能のサポートは含まれていません。 Teams ユーザーに対して CCE または OPCH を使用する PSTN 通話機能を有効にすることはできません。

### <a name="interop-experiences-limitations"></a>相互運用エクスペリエンスの制限
現時点では、Teams と Skype for Business 間において統一された表示形式が確立されていないため、Teams と Skype for Business ではそれぞれ独自の表示形式が採用されています。さらに、Teams と Skype for Business 間でのチャットと通話の相互運用エクスペリエンスで利用できない機能もあります。

チャットの相互運用における現在の制限を次に示します。
- Teams でのマルチパーティ (グループ) の会話 (チャット) には Teams を使用する参加者のみを含めることができます
- Skype for Business でのマルチパーティ IM 会話 (チャット) には Skype for Business を使用する参加者のみを含めることができます
- Teams と Skype for Business 間における 2 つのパーティ間のチャット会話でのファイル転送またはマルチパーティの会話でのファイルの添付はサポートされていません
- Teams ではチャットの相互運用は継続されません
- 相互運用チャットでは、Teams のマークダウン、リッチ テキスト、絵文字のセットはサポートされません

通話の相互運用における現在の制限を次に示します。
- Teams と Skype for Business 間の画面共有 (デスクトップまたはアプリの共有) はサポートされません
- 現在使用中のピアツーピア (P2P) の音声通話やビデオ通話を Teams と Skype for Business ユーザーによるマルチパーティ通話に昇格させることはできません

## <a name="managing-interoperability"></a>相互運用性の管理
Teams と Skype for Business 間の相互運用性を管理するため、Teams 相互運用ポリシーという新しいポリシーを使用して、チャットの送信先や通話のルーティング経路を Teams または Skype for Business のいずれかに制御できます。このポリシーは、組織のすべてのユーザーに設定するか (グローバル ポリシー)、ユーザーごとに適用することができます。こうした管理は [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) コマンドレットを使用して Skype for Business の Windows PowerShell リモート セッションを開いて行うことができます。

既定では、このポリシーは、Teams と Skype for Business が最小限の相互運用を確保しつつ共存する形で使用されるよう設定されています。 このアプローチは Teams の導入により組織の現在のビジネス プロセスと通信に中断が発生しないようにすることを目的としています。

### <a name="interop-policy-overview"></a>相互運用ポリシーの概要
Teams の相互運用ポリシーは次のパラメーターで構成されています。

|パラメーター                    |可能な値      |説明  |
|-----------------------------|---------------------|---------|
|`ChatDefaultClient`          | Default、SfB、Teams | このパラメーターは既定のチャット アプリを指定します        |
|`CallingDefaultClient`       | Default、SfB、Teams | このパラメーターは既定の通話アプリを指定します        |
|`AllowEndUserClientOverride` | True、False         | このパラメーターはユーザーが既定のチャット アプリや通話アプリを上書きできるかどうかを指定します         |

> [!WARNING]
> 現時点では、`ChatDefaultClient` と `CallingDefaultClient` パラメーターに独立した値を指定して Teams の相互運用ポリシーを作成することができますが、これは将来的に変更される予定です。 現時点では、両方のパラメーターに同じ値を指定してください。

#### <a name="chat-default-client"></a>チャットの既定のクライアント
`ChatDefaultClient` パラメーターでは、Teams と Skype for Business 間におけるチャットのルーティング経路を定義します。このパラメーターの既定のグローバル値は **Default** に設定されています。

> [!IMPORTANT]
> 現時点では、Teams で `ChatDefaultClient` パラメーターは重視されません。 Teams でこのパラメーターが重視されるようになった際は、このドキュメントを更新して予期される動作を記載する予定です。 テナント レベルで制御される Teams と Skype for Business 間のチャットの既存の相互運用はこれまでどおり継続的に機能します。

#### <a name="calling-default-client"></a>通話の既定のクライアント
`CallingDefaultClient` パラメーターでは、Teams と Skype for Business 間における通話のルーティング経路を定義します。このパラメーターの既定のグローバル値は **Default** に設定されています。

次に、このパラメーターの設定が Teams と Skype for Business のクライアントの動作に及ぼす影響について詳しく説明します。

|発信者の通話元  |設定: Default; 通話の受信先  |設定: Teams; 通話の受信先  |設定: SfB; 通話の受信先  |
|---------|---------|---------|---------|
|**Skype for Business**     |Skype for Business         |Teams        |Skype for Business         |
|**Teams**     |Teams         |Teams         |Skype for Business         |
|**PSTN**   |Skype for Business        |Teams        |Skype for Business         |
|**フェデレーション Skype for Business**     |Skype for Business         |Skype for Business         |Skype for Business         |

> [!IMPORTANT]
> 現時点では、`CallingDefaultClient` を Teams に変更すると、Skype for Business IP 電話への通話にも影響を及ぼします。 Skype for Business IP 電話で着信通話を受信できなくなり、Teams クライアントでのみ着信音が鳴ります。 既存の認定済み SIP 電話のサポートについては、「[Skype for Business から Microsoft Teams へ: 機能のロードマップ](https://aka.ms/skype2teamsroadmap)」をご覧ください。

#### <a name="allowing-user-choice"></a>ユーザーの選択を許可する
`AllowEndUserClientOverride` パラメーターにはブール値 (**TRUE** または **FALSE**) を指定できます。**TRUE** に設定すると、Teams でユーザーは通話の受信先 (Teams または Skype for Business) を選択することができ、使用する主なアプリケーションをいつでも変更できます。

![優先する通話アプリケーションのオプション](media/Preferred_calling_application_option.png)

このパラメーターのグローバル既定値は **FALSE** です。ユーザーは使用する主なアプリケーションを管理者の介入なしに選択することはできません。

## <a name="teams-interop-policy-special-cases"></a>Teams の相互運用ポリシーの特殊なケース
Teams の相互運用ポリシーを割り当てる際に、混在 (ハイブリッド) 展開トポロジの Skype for Business オンプレミスに所属したままになっているユーザー、Hybrid Voice を CCE または OPCH のいずれかを介して使用するユーザー、特化した Skype for Business ワークフローを使用するユーザーは特殊なケースとして考慮されます。こうしたユーザーに割り当てるポリシーには特別な注意を払う必要があります。

### <a name="policy-for-skype-for-business-on-premises-users"></a>Skype for Business オンプレミス ユーザーのポリシー
混在 (ハイブリッド) 展開トポロジでは、Skype for Business オンプレミスに所属するユーザーのポリシーで `ChatDefaultClient` と `CallingDefaultClient` パラメーターを Teams に設定しないでください。 そのように設定すると、チャットや通話を受信できなくなります。 オンプレミス ユーザーについては次のポリシー定義を使用します。

|パラメーター  |値  |
|---------|---------|
|`ChatDefaultClient`    |Default または SfB         |
|`CallingDefaultClient`     |Default または SfB         |
|`AllowEndUserClientOverride`     |False         |

> [!IMPORTANT]
> Skype for Business Online から Skype for Business オンプレミス (またはその逆) にユーザーを移動する場合は、そのユーザーに割り当てられた Teams の相互運用ポリシーが、適用する必要のある動作に対して同調していることを確認する必要があります。 オンプレミス ユーザーは Teams を主に使用するチャットや通話のアプリケーションとして設定できないことに注意してください。

### <a name="policy-for-hybrid-voice-users-cce-or-opch"></a>Hybrid Voice ユーザーのポリシー (CCE または OPCH)
Hybrid Voice を (CCE または OPCH を介して) 利用する電話システムが有効な Skype for Business Online ユーザーは Teams で PSTN 通話を受信することはできません。 Teams の相互運用ポリシーを Hybrid Voice ユーザーに割り当てる際には、次のポリシー定義を使用します

|パラメーター  |値  |
|---------|---------|
|`ChatDefaultClient`    |Default、SfB、または Teams         |
|`CallingDefaultClient`     |Default または SfB         |
|`AllowEndUserClientOverride`     |False         |

### <a name="policy-for-users-with-specialized-skype-for-business-workflows"></a>特化した Skype for Business ワークフローを使用するユーザーのポリシー
場合によっては、ユーザーのグループが、Skype for Business に依存するサード パーティのアプリケーションを使用していることがあります (例: コール センター、フロント デスク受付担当者など)。 このような場合には、同等の機能が Teams で利用可能になるまでこれまでどおり Skype for Business を使用してもらいます。 こうしたユーザーには、次のポリシー定義を使用します。

|パラメーター  |値  |
|---------|---------|
|`ChatDefaultClient`    |Default または SfB         |
|`CallingDefaultClient`     |Default または SfB         |
|`AllowEndUserClientOverride`     |False         |