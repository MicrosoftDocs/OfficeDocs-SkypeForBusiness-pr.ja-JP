---
title: "Microsoft チーム」と「Skype for Business の相互運用性"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "ビジネス チャットとエクスペリエンスの呼び出しの外観をチームと Skype の間の相互運用性を理解します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8eca9f18d02d76fe1ab1b754ecf8a49b6b20aec3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="microsoft-teams-and-skype-for-business-interoperability"></a>Microsoft チーム」と「Skype for Business の相互運用性
=======================================================

組織が使用して Skype for Business 今日場合は、チームの使用を開始するには、2 つの相互運用するアプリケーションを構成する方法を理解する必要があります。

> [!IMPORTANT]
> プランの呼び出しのサポート チームの初期評価については、このドキュメントが表示されます。チームの相互運用ポリシーの詳細については、今後、変更する必要があります。

(短い形式の相互運用性) の相互運用性により、Skype for Business とチームのユーザーをチャットし、そのコミュニケーション、通話、組織全体で滑らかをそのまま保持します。IT プロフェッショナルはチームの導入を管理するために、追加した新しいチーム相互運用ポリシー、Skype for Business リモート Windows PowerShell セッションを使用してを通して管理[`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)コマンドレットします。チームの組織で必要に操作するのに方法を構成するのにには、このポリシーを使用します。


> [!TIP]
> 相互運用に必要な PowerShell コマンドレットを検索するには、 [Skype for Business PowerShell コマンドレットのドキュメント](https://docs.microsoft.com/powershell/module/skype)で**フィルター** ] ボックスに"CsTeamsInteropPolicy"を入力します。

チームの相互運用ポリシーは、IT プロフェッショナル チャットと通話を受信するユーザーの任意のアプリケーションを指定するのには使用できます。チームと Skype for Business、孤立の通信を維持するように構成できるまたはアプリケーションの境界を超えた通信するためにユーザーを有効にするように構成できます。

チームの相互運用ポリシーは、テナント レベルまたはユーザーごとのレベルで定義されることができ、使ってがチャットと通話を受信するには、どのようなアプリケーションを選択するユーザーを有効にも構成されていることができます。

この組み込みの柔軟性が、組織の試用版のヘルプ、評価、およびペースでと、組織に最適な方法でチームに移行する想定しています。

> [!NOTE]
> チームと Skype for Business の間の相互運用性が純オンライン (Skype for Business Online やチーム)、ユーザーの間でサポートされているし、Skype for 混在 (ハイブリッド) 展開トポロジでビジネスのオンプレミス展開でユーザーが存在します。

## <a name="what-interoperability-means"></a>どのような相互運用性を意味します。
相互運用性は、チャット (IM) のビジネス ユーザーのチームと Skype の機能で互いをチームと Skype for Business 通話します。

組織では、Skype for Business からチームへの旅を開始、予想は、組織内で別のクライアントを使用しているユーザーの組み合わせがあるされます。

"続く"の生産性を確認するには、チームには、ユーザーと通信するいずれかの別のアプリケーションに関係なく (チームまたは Skype for Business) を使用する機能が用意されています。

サポートされているの相互運用エクスペリエンス、次のとおりです。
- Skype for Business ユーザー チームを使用していないチャットできるは、チームのユーザー間で変換<p>
![チームからの相互運用チャット エクスペリエンス](media/Interop_chat_experience_from_Teams.png)<br>
- Skype for Business ユーザー音声やビデオの上には、チームのユーザーを転換呼び出すことができます。詳細呼び出しのオプション] で、着信の転送と、着信の転送など、作業を続けられます、相互運用呼び出しに対してもします。<p>
![チームからの相互運用呼び出しエクスペリエンス](media/Interop_calling_experience_from_Teams.png)<br>

> [!NOTE]
> ビジネス ユーザーの観点の Skype からチャットとからウィンドウにドッキング、チーム呼び出しは、基本的な Skype for Business チャットと通話として表示されます。詳細については、[相互運用性の制限事項が発生した](#interop-experiences-limitations)のセクションを参照してください。

> [!IMPORTANT]
> チームと Skype for Business の統合されたプレゼンス現在、サポートされていないことを意味チームと Skype for Business で独自の独立したプレゼンス状態が表示されます。サポート プレゼンスの統合を調べるにはできるように、 [Skype for Business に Microsoft チーム機能ロードマップ](https://aka.ms/skype2teamsroadmap)を確認します。

## <a name="interop-requirements"></a>相互運用機能の要件
相互運用の機能を有効にする、ユーザーは次の抽出条件を満たす必要があります。
- ユーザーする必要がありますが有効になっている (またはライセンスが付与されて) チーム
- ユーザーする必要がありますが有効になっている (またはライセンスが付与されて) Skype for Business Online の
    - これは、プライマリ チャット呼び出し元のアプリケーションとチームをのみを使用することを計画しているユーザーまたはチームに適用されます。
- ビジネス展開の場合は、ハイブリッド Skype で
    - クラウドのユーザーがチームを使用してビジネス (または現在 Business ハイブリッド展開の Skype でサポートされているすべての Lync Server バージョン) の内部設置型の Skype のユーザーが存在、相互運用性
    - クラウドのユーザーのプライマリ チャットとしてチームの使用を計画、アプリケーションの呼び出しをする必要がありますが有効になっている (またはライセンスが付与されて) Skype for Business Online の

## <a name="supported-topologies-for-interop"></a>サポートされているトポロジの相互運用性
チームと Skype for Business の間の相互運用性は主に以下 Skype for Business の展開トポロジのサポートされています。
- Skype for Business Online のみ
- Skype for Business (混在 Skype の展開 Business Online と Skype for Business オンプレミス用)

### <a name="skype-for-business-online-only-topology"></a>Business Online のみトポロジの Skype
のみ Skype for Business Online 展開組織は、チャットの相互運用と Skype for Business Online のユーザーとチームのユーザーの呼び出し元のサポートを利用できます。

このトポロジでプライマリ チャットとしてチームと、ユーザーが設定されているし、呼び出し元のアプリケーションも有効化が必要 skype for Business Online の相互運用性関数にします。

![Skype for Business Online のみ展開トポロジの相互運用性](media/Interop_SkypeforBusinessOnlineOnly_topology.png)

### <a name="skype-for-business-hybrid-deployment-topology"></a>Skype for Business のハイブリッド展開のトポロジ
Skype for Business Online と Skype for Business 組み合わせた展開の構成の展開を持つ組織サーバー (オンプレミス) のハイブリッド展開トポロジでは、役に立つ相互運用チャットと Skype for Business のユーザー (ホームが間呼び出しのサポートいずれかのオンラインや社内)、およびチームのユーザー。

同様に Business Online のみ展開トポロジの Skype、プライマリ チャットとしてチームと、ユーザーが設定されているアプリケーションを呼び出す必要がありますもは用に有効に存在してで Skype for Business Online 関数には、相互運用性の。

![Skype for Business のハイブリッド展開のトポロジの相互運用性](media/Interop_SkypeforBusinessHybrid_topology.png)

> [!IMPORTANT]
> Skype for Business の相互運用サポート CCE (クラウド コネクタ エディション) 経由で配信ハイブリッド音声機能は含まれませんまたはオンプレミス PSTN 接続 - 既存の展開を使用するか、OPCH ([Prem 構成ハイブリッド) として一般的と呼ばれます。チームのユーザーは PSTN 通話の CCE または OPCH を使用する機能を有効にすることはできません。

### <a name="interop-experiences-limitations"></a>相互運用エクスペリエンスの制限事項
現在、チームと Skype for Business で、チームと Skype for Business の自分の独立したプレゼンス状態が発生する潜在顧客、統合されたプレゼンスがない場合以外は相互運用チャットと相互運用呼び出しを利用できない機能チームと Skype for Business のエクスペリエンスします。

チャットの相互運用には、次の制限事項の現在のリストです。
- チームで複数のパーティー (グループ) の会話 (チャット) は、チームを使用する参加者を含めることができますのみ
- マルチパーティ IM 会話 (チャット) Skype for Business では、Skype for Business 使い参加者を含めることができますのみ
- 2 者間のチャットの会話またはチームと Skype for Business では、複数の会話でファイルの添付ファイルのファイル転送間の切り替えはサポートされません。
- チームの相互運用チャットは保持されません。
- 値下げ、リッチ テキスト、完全な絵文字セット、相互運用チャットのチームでなどがサポートされていません

呼び出しの相互運用には、次の制限事項の現在のリストです。
- スクリーン (デスクトップまたはアプリケーションの共有) をチームと Skype for Business の共有はサポートされていません
- ピア ツー ピア (P2P) の進行中の音声とビデオ通話をチームと Skype のビジネス ユーザーの検出しやすくマルチパーティの通話の昇格はサポートされていません

## <a name="managing-interoperability"></a>管理の相互運用性
チームと Skype for Business の間の相互運用性を管理するには、チームの相互運用ポリシーと呼ばれる新しいポリシーを使用して、位置の制御をチャットの送信、通話をルーティングするには、チームの組織内のすべてのユーザーは、Skype for Business、およびこのポリシーを構成することができます。(グローバル ポリシー) または Business リモート Windows PowerShell セッションを使う場合の Skype を管理しやすく、ユーザーごとに適用される[`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)コマンドレットします。

既定では、このポリシーように構成されてチームと Skype for Business できる間に最低限の相互運用性と並行して使用することを確認します。この方法は、現在のビジネス プロセスと、組織内の通信が中断するチーム導入の結果としてことを確認します。

### <a name="interop-policy-overview"></a>相互運用ポリシーの概要
チームの相互運用ポリシーは、次のパラメーターで構成されます。

|パラメーター                    |指定可能な値      |説明  |
|-----------------------------|---------------------|---------|
|`ChatDefaultClient`          | 既定のデバイス、チーム | このパラメーターは、チャットの既定のアプリを指定します。        |
|`CallingDefaultClient`       | 既定のデバイス、チーム | このパラメーターは、通話の既定のアプリを指定します。        |
|`AllowEndUserClientOverride` | True、false の場合         | このパラメーターは、ユーザーが既定のチャットとアプリの呼び出しを上書きできるかどうかを指定します。         |

> [!WARNING]
> 現在の独立した値を持つチームの相互運用ポリシーを作成することはできますが`ChatDefaultClient`と`CallingDefaultClient`パラメーターを考えて、今後、変更します。この時点で確認してください両方のパラメーターの値を使用しています。

#### <a name="chat-default-client"></a>チャットの既定のクライアント
[`ChatDefaultClient`チームと Skype for Business] の [チャットのルーティング方法を定義して、このパラメーターのグローバル既定値は、**既定**に設定されています。

> [!IMPORTANT]
> 、現時点では、`ChatDefaultClient`パラメーターはチームが尊重されません。チームが尊重パラメーターと想定される動作を説明するには、このドキュメントが更新されます。チームと Skype for Business のテナント レベルで管理されている間は、既存のチャット相互運用機能は引き続き機能はします。

#### <a name="calling-default-client"></a>通話の既定のクライアント
`CallingDefaultClient`チームと Skype for Business で通話をルーティングする方法を定義して、このパラメーターのグローバル既定値は、**既定**に設定されています。

このパラメーターの各値に影響するしくみチームと Skype for Business クライアントの動作の詳細な説明を次に示します。

|発信者からを呼び出す  |既定の設定:通話の受信  |チームの設定:通話の受信  |デバイスの設定: です。通話の受信  |
|---------|---------|---------|---------|
|**Skype for Business**     |Skype for Business         |チーム        |Skype for Business         |
|**チーム**     |チーム         |チーム         |Skype for Business         |
|**PSTN**   |Skype for Business        |チーム        |Skype for Business         |
|**フェデレーションの Skype for Business**     |Skype for Business         |Skype for Business         |Skype for Business         |

> [!IMPORTANT]
> 現時点では、変更する`CallingDefaultClient`チームにも影響 skype 通話ビジネス IP 電話用します。着信通話られ、携帯電話に受信できませんが、リング チーム クライアントのみをされます。既存の認定 SIP 電話のサポートについては、 [Skype for Business に Microsoft チーム機能ロードマップ](https://aka.ms/skype2teamsroadmap)を参照してください。

#### <a name="allowing-user-choice"></a>ユーザーの選択を許可します。
`AllowEndUserClientOverride`パラメーターがブール値 (**TRUE**または**FALSE**) を受け入れるし、チームがチームまたは Skype for Business、-、通話を受信する必要があると、ユーザーが、プライマリを変更できる場所を選択する許可を持つ**TRUE**に設定されている場合いつでもアプリケーションです。

![好みの呼び出し元アプリケーション オプション](media/Preferred_calling_application_option.png)

このパラメーターのグローバル既定値が**FALSE**されないようにユーザーは可能管理者からしなくても、プライマリ アプリケーションを選択します。

## <a name="teams-interop-policy-special-cases"></a>チームの相互運用ポリシーの特殊な場合
チームの相互運用ポリシー、ビジネス オンプレミス--混在 (ハイブリッド) 展開トポロジでの Skype のホームに残っているユーザーに割り当てる (両方 CCE や OPCH)、ハイブリッドの音声を持つユーザーとビジネス ワークフローの特殊な skype ユーザーと見なされ、特殊な場合は、およびが割り当てられているポリシーに特別な注意が必要です。

### <a name="policy-for-skype-for-business-on-premises-users"></a>Skype for Business のポリシー オンプレミス ユーザー
混合 (ハイブリッド) 展開トポロジでは、ユーザーが所属 Skype でのビジネス オンプレミスにチームのいずれかの設定、ポリシーを使用する必要はありません`ChatDefaultClient`と`CallingDefaultClient`パラメーターします。存在する場合は、することはできませんチャットと通話を受信します。オンプレミスのユーザーには、次のポリシーの定義を使用します。

|パラメーター  |値  |
|---------|---------|
|`ChatDefaultClient`    |既定のグループまたはデバイス         |
|`CallingDefaultClient`     |既定のグループまたはデバイス         |
|`AllowEndUserClientOverride`     |False         |

> [!IMPORTANT]
> ユーザー Skype から for Business Online に移動 Skype for Business、社内でときに、その逆の動作を適用する必要のあるユーザーに割り当てられているチームの相互運用ポリシーが配置されたかどうかを確認する必要があります。プライマリ チャット アプリケーションを呼び出すとチームを使用するオンプレミスのユーザーを構成できないことにご注意ください。

### <a name="policy-for-hybrid-voice-users-cce-or-opch"></a>ハイブリッド ボイス ユーザー (CCE または OPCH) のポリシー
Skype for Business Online のユーザーがハイブリッドの音声 (CCE または OPCH) 経由で電話システム用に有効には、チームで PSTN 通話を受信することはできません。ハイブリッド ボイス ユーザーのチームの相互運用ポリシーを割り当てる場合は、次のポリシーの定義を使用します。

|パラメーター  |値  |
|---------|---------|
|`ChatDefaultClient`    |既定のデバイスまたはチーム         |
|`CallingDefaultClient`     |既定のグループまたはデバイス         |
|`AllowEndUserClientOverride`     |False         |

### <a name="policy-for-users-with-specialized-skype-for-business-workflows"></a>ビジネス ワークフローの特殊な Skype でのユーザーに対してポリシー
場合によっては、ユーザーのグループを使用している可能性 Skype for Business に依存するサードパーティのアプリケーション (例:: センター、受付応答などの着信します。) します。場合、次のことが必要になるまで、チーム内と同じ機能がある Skype for Business で維持するためにします。これらのユーザーでは、次のポリシーの定義を使用します。

|パラメーター  |値  |
|---------|---------|
|`ChatDefaultClient`    |既定のグループまたはデバイス         |
|`CallingDefaultClient`     |既定のグループまたはデバイス         |
|`AllowEndUserClientOverride`     |False         |