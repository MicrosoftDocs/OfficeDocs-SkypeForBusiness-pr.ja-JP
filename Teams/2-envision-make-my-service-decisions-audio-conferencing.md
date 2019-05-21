---
title: 電話会議のサービスに関する決定を行う - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 会議、ライセンスと可用性、会議ブリッジの設定の構成、電話番号の取得または転送、テナントダイヤルプランの選択について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3867f7f2f9dd2f093b71ced40b0c07b6c5395041
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400906"
---
# <a name="make-my-service-decisions"></a>サービスの決定を行う

電話会議の技術的な実装を計画するには、定義済みのビジネス要件を満たすソリューションを実装するために、事前に一連のサービス決定を行う必要があります。

## <a name="audio-conferencing-in-teams"></a>Teams での電話会議

Microsoft Teams で必要な電話会議機能の定義の一環として、最初の手順の1つとして、最新のパブリックロードマップを評価して次のことを決定します。

-   スコープ内のユーザーに対して展開されるチームの電話会議機能。

-   Teams の電話会議には、予期されるユーザー機能の要件があります。

-   最新のパブリックロードマップに記載されているチームの電話会議機能が、展開のタイムライン内でユーザー、機能、およびスコープの要件を満たしていることを確認します。

> [!NOTE]
> 展開の範囲で Teams の音声会議機能を特定するための最新の Teams ロードマップ<https://aka.ms/O365Roadmap>は、にあります。

## <a name="meetings-in-teams"></a>Teams での会議

Teams では、HD ビデオ、ボイスオーバー IP (VoIP)、PSTN のダイヤルイン会議のオプションを使って、オンライン会議のスケジュールを設定し、参加することができます。

会議は、プライベート会議 (招待されたパーティのみ参加可能) またはチャネル会議 (チャネルへのアクセス権を持つすべてのユーザーに対して開く) としてスケジュールできます。また、ユーザーはチャネル内で一時的会議を開始することもできます。

> [!NOTE]
> Teams での会議の機能の詳細については、 [Microsoft 365 のロードマップ](https://aka.ms/O365Roadmap)を参照してください。

会議の参加者は、固定電話または携帯電話を使用して、有料または無料のダイヤルイン会議ブリッジの電話番号にダイヤルインして、チーム会議に参加することができます。 さらに、電話会議サービスに "コールイン" 機能を開始させて、会議に参加できるようにすることもできます (データ接続の信頼性が低い場合に便利です)。または、会議の開催者に会議の出席を依頼してもらうこともできます。参加者の電話にダイヤルアウトしてください。

> [!IMPORTANT]
> Teams の電話会議では、サードパーティの電話会議プロバイダー (ACPs) をサポートしていません。

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>電話会議の利用可否

Teams で電話会議の実装を計画する前に、電話[会議と通話プランの国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)について詳しく説明しているように、電話会議サービスが利用可能かどうかを確認する必要があります。

> [!IMPORTANT]
> 電話会議が多国籍組織で利用できるようにするには、法的な制約があるため、電話会議サービスが市販されている国と地域から Office 365 サブスクリプションの契約を受ける必要があります。

組織が電話会議サービスを入手する資格があることを確認したら、利用可能な国と地域の一覧に基づいて、電話会議サービスを実装するユーザーの場所またはオフィスのリストをコンパイルします。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断のポイント|<ul><li>電話会議サービスを実装するユーザーの場所またはオフィスを決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>電話会議サービス用に有効にするユーザーの場所またはオフィスを文書化します。</li></ul>|

> [!TIP]
> 電話会議サイトの有効化リストテンプレートの例を次に示します。
> 
> |Office   |場所 |PSTN 会議サービス  |
> |---------|---------|---------|
> |One Epping Road|オーストラリア|電話会議|
> |100 Cyberport Road|香港特別自治区|旧 PSTN 会議|
> |One Marina Boulevard|シンガポール|電話会議|
> |32 London Bridge Street|イギリス|電話会議|
> |39 quai du Président Roosevelt|フランス|電話会議|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>電話会議のライセンス

[電話会議ライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)は、Office 365 E5 サブスクリプションプランの一部として、または Office 365 E1 または Office 365 E3 サブスクリプションプランのアドオンサービスとして利用できます。

> [!NOTE]
> Teams の PSTN またはダイヤルイン会議は、サードパーティの電話会議プロバイダー (ACPs) をサポートしていません。
> <br>Skype for Business Online PSTN 会議を使用している場合は、Teams ですぐに電話会議を利用できます。

無料電話会議用の電話番号を提供し、国際電話番号への会議のダイヤルアウトをサポートするには、組織の[通信クレジット](what-are-communications-credits.md)を設定する必要があります。

> [!IMPORTANT]
> 一部の国では、無料の電話会議の電話番号のみが対象としています。 これらの国でダイヤルインをサポートするには、通信クレジットを使用する必要があります。

通信クレジットを導入する際の最初の考慮事項は、購入する資金の最初の金額を決定することです。 組織で自動再充電を選択する場合は、トリガー金額 (最低金額) と自動再充電金額を決定する必要があります。 実際の使用状況により、自動再充電金額が決定されます。 通信クレジットの使用状況は、時間の経過に応じて監視し、必要に応じて再充電金額を調整する必要があります。

通信クレジットの詳細については、[こちら](what-are-communications-credits.md)をご覧ください。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断のポイント|<ul><li>組織で、必要な電話会議ライセンスをまだ購入していない場合は、既存の Office 365 サブスクリプションをステップアップするか、電話会議のアドオンライセンスを取得して、電話会議ライセンスを取得するかどうかを決定します。</li><li>電話会議の実装で通信クレジットが必要かどうかを決定します。 必要な場合は、初回購入金額を決定します。 該当する場合は、リチャージを実行する金額と自動リチャージする金額を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>電話会議ライセンスが割り当てられたユーザーを文書化します。</li><li>通信クレジットプランを文書化する (初期金額、開始金額、自動再充電金額)</li></ul>|

> [!TIP]
> 次の例を使用して、電話会議ユーザーのライセンス割り当てリストを文書化することができます。
> 
> |ユーザー  |オフィス  |Office 365 ライセンス  |
> |---------|---------|---------|
> |Adele Vance|One Epping Road|Office 365 E5|
> |Alex Wilber|One Epping Road|Office 365 E3、電話会議アドオン|
> |Ben Walters|One Epping Road|Office 365 E3、電話会議アドオン|
> |Christie Cline|One Marina Boulevard|Office 365 E3、電話会議アドオン|
> |Debra Berger|One Marina Boulevard|Office 365 E5|
> |Lee Gu|One Marina Boulevard|Office 365 E5|
> |Emily Braun|32 London Bridge Street|Office 365 E5|
> |Lidia Holloway|32 London Bridge Street|Office 365 E5|
> |ルイス Lahr|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3、電話会議アドオン|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3、電話会議アドオン|

<br>

> [!TIP]
> コミュニケーション クレジットを適用する電話番号を次のように文書化することができます。
>
> |         |         |
> |---------|---------|
> |初回購入金額|$ 1,000|
> |リチャージを実行する金額|$400|
> |自動リチャージする金額|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>会議ブリッジ電話番号

Office 365 の電話会議サービスには次が含まれます。

-   複数の種類の会議ブリッジ電話番号 (有料および有料)

-   電話会議の電話番号の複数カテゴリ (専用および共有)

-   会議ブリッジでの複数言語のサポート (プライマリとセカンダリ)

-   テナントの既定の電話番号

> [!NOTE]
> 専用電話会議の電話番号は、該当するライセンスの数に基づいて、テナントごとに取得可能な電話番号の上限にカウントされます。 無料電話の会議ブリッジ電話番号では通信クレジットが必要になります。

電話会議サービスに、国固有の要件を満たしていることを前提として、既存の電話番号を転送する必要がある場合は、これらの既存の会議ブリッジの電話番号を Microsoft に移行できます。

> [!NOTE]
> Microsoft への電話番号の移行の複雑さは、国または地域、通信事業者、関連する回路の数、その他多くの要素によって大きく異なります。 現在のプロバイダーと協力して、タイムラインに合わせてプロセスを早めに開始するために必要な時間を調査します。

会議ブリッジの電話番号の詳細については、次の記事を参照してください。

-   [Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)

-   [電話会議の電話番号](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [サービス電話番号を取得する](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

-   [Office 365 に電話番号を転送する](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断のポイント|<ul><li>組織で専用の電話会議用の電話番号が必要かどうかを決定します。</li><li>電話会議の実装の範囲内のユーザーの場所またはオフィスに対して、専用の電話番号を取得する方法を決定します (つまり、Microsoft から取得するか、既存の電話番号を転送します)。</li><li>Microsoft から入手することを選んだ場合は、電話会議の実装の範囲内のユーザーの場所またはオフィスに対して、使用する方法 (フォームの申請または自動) を決定します。</li><li>専用の電話会議用の電話番号ごとに設定する言語設定を決定します。</li><li>テナントの既定の会議ブリッジの電話番号を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>電話番号を取得するためのマスタープランを文書化します。電話会議の実装について、各ユーザーの場所または office の範囲で電話番号を取得する方法が詳しく説明されています。</li><li>該当する場合は、新しい電話番号の申請フォームに記入します。場所または会社ごとに1つのフォームに入力します。</li><li>詳細な会議ブリッジの電話番号構成 (共有および専用の会議ブリッジの電話番号、各専用の電話会議の電話番号、テナントの既定の電話番号の言語設定など) を文書化します。</li></ul>|

次に示すのは、会議ブリッジの詳細をキャプチャするために使用できるテンプレートの例です。

> [!TIP]
> 以下に電話会議の詳細を取得するためのテンプレートの例を示します。
> 
> |オフィス   |ブリッジ番号の取得とブリッジの種類 |ブリッジ番号  |ブリッジの言語|
> |---------|---------|---------|---------|
> |One Epping Road|新規に取得、専用|TBA|英語 (オーストラリア)|
> |One Marina Boulevard|新規に取得、共有|TBA|英語 (米国)、中国語 (簡体字、PRC)|
> |32 London Bridge Street|既存のポート、専用|+44 20 7946 0001|英語 (英国)|
> |39 quai du Président Roosevelt|新規に取得、専用|TBA|フランス語 (フランス)、英語 (英国)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>会議ブリッジの設定

ユーザーエクスペリエンスをさらに調整するために、電話会議に参加するための組織全体のオプション (会議の入場と退出通知、発信者番号の記録)、会議開催者の PIN の長さ、およびメールの通知を構成することができます。

-   会議の参加と退出に関する通知は、記録された名前、電話番号、効果音の形式で利用できます。

-   PIN の長さは 4～12 桁です。既定は 5 桁の PIN です。

-   電話会議ライセンスまたは他の管理者による変更を有効にして送信された通知メールは、既定で有効になっています。 この機能を無効にして、組織のユーザーの通信を制御することができます。

電話会議ライセンスが割り当てられているユーザーについては、電話会議の座標に表示される既定の有料電話番号または無料電話番号は、次の機能を使用するように構成できます。

-   テナントレベルの既定。

-   自動的に割り当てられた会議ブリッジの電話番号。

-   ユーザーごとに手動で構成された会議ブリッジの電話番号。

ユーザー固有の会議ブリッジの電話番号は、通常、ユーザーが配布され、会議出席依頼の既定の電話番号として市内番号を提供する必要があるグローバルまたは全国の組織で役立ちます。

複数の都市または海外から参加している参加者は、テナントレベルで構成された追加の番号を検索できますが、これらの番号は、会議出席依頼に直接表示されません。 会議出席依頼には、参加者が [ **Teams 会議のダイヤルイン番号**] ページに移動して、その場所に最も近い電話会議番号を検索するリンクが用意されています。

また、認証されていない発信者が会議を開始することを許可して、認証されていない発信者が参加できるようにする必要があるかどうか、または認証されていない発信者に会議の開始を許可するかどうかを構成することもできます。.

また、ユーザーごとに追加の構成を適用して、無料電話会議の電話番号の使用を制御したり、会議からダイヤルアウトしたりすることもできます。

> [!NOTE]
> このコスト関連のコントロールは、現在、プレビュー版のお客様のみが利用できます。 プレビュープログラムでは、からhttps://www.skypepreview.com組織を登録できます。

これらのコントロールを使用して、会議の開催者が会議用の電話番号を提供できるかどうかを決定できます。会議の開催者は、会議の開催者が開催した会議について、参加者が自分の会議をダイヤルアウトすることができます。 ダイヤルアウトのレベルは完全にダイヤルできないようにし、国内の番号へのダイヤルアウトを許可するために、国内の番号と国際電話の両方の番号へのダイヤルアウトを許可します。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断のポイント|<ul><li>組織で入力通知と終了通知が必要かどうかを決定します。その場合は、実装する通知の種類 (トーン、電話番号、または記録された名前) を指定します。</li><li>組織のセキュリティ要件を満たす電話会議の PIN の長さを決定します。</li><li>電話会議サービスに関連するユーザーの通信を組織で制御するかどうかを決定します。</li><li>各会議の開催者に割り当てる会議ブリッジの電話番号を決定します。</li><li>会議の開催者が、会議用に無料電話会議用の電話番号を使用する必要があるかどうかを決定します。</li><li>会議の開催者が、認証されていない発信者に会議の開始を許可する必要があるかどうかを決定します。</li><li>会議の開催者が会議のダイヤルアウトを管理する必要があるかどうかを決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>会議ブリッジの詳細設定 (エントリと終了の通知、PIN の長さ、構成変更のメール通知の設定) を文書化する</li><li>各会議の開催者に割り当てられる会議ブリッジの電話番号と、認証されていない発信者のポリシーを制御するための対応する設定、および無料とダイヤルアウトのコントロールについて文書化します。</li></ul>|

> [!TIP]
> 次の例のように、会議ブリッジの設定を文書化することができます。
> 
> |         |         |
> |---------|---------|
> |会議の入場と退場の通知を有効にする|有効|
> |入場と出口のアナウンスの種類|鳴り|
> |会議に参加する前に、発信者に名前を記録するように依頼する|無効|
> |PIN の長さ|5|
> |ダイヤルイン設定が変更されると、ユーザーにメールが自動的に送信される|無効|

<br>

> [!TIP]
> 次の例を使用して、電話会議ユーザー用の会議ブリッジ設定の割り当てリストを文書化することができます。
>
> |ユーザー  |オフィス  |既定の有料電話番号  |既定の無料電話番号  |無料通話を許可する  |認証されていない発信者がロビーをバイパス  |会議のダイヤルアウト  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|One Epping Road|TBA|TBA|はい|有効|国際および国内|
> |Alex Wilber|One Epping Road|TBA|TBA|いいえ|無効|許可しない|
> |Ben Walters|One Epping Road|TBA|TBA|いいえ|無効|許可しない|
> |Christie Cline|One Marina Boulevard|TBA|TBA|はい|無効|市外|
> |Debra Berger|One Marina Boulevard|TBA|TBA|はい|有効|市外|
> |Lee Gu|One Marina Boulevard|TBA|TBA|はい|有効|市外|
> |Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|はい|有効|許可しない|
> |Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|はい|無効|許可しない|
> |ルイス Lahr|32 London Bridge Street|+44 20 7946 0001|TBA|はい|無効|許可しない|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|いいえ|無効|市外|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|はい|有効|国際および国内|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|いいえ|無効|市外|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>クラウドのボイス電話番号を管理する

電話会議の実装では、新しい電話番号を取得するか、既存の電話番号を移行/移植するかを選ぶことができます。

市内通話の市外局番の表示、国内通話の国コードの除外、会議のダイヤルアウトを実行するときに短い桁のダイヤルを使用して、ユーザーが使い慣れた方法で電話番号をダイヤルできるようにするには、カスタマイズされたダイヤルプランを構成できます。ユーザーに割り当てることができます。

## <a name="acquire-new-telephone-numbers"></a>新しい電話番号を取得

Microsoft cloud voice solutions に含まれる電話番号には、次の2種類があります。

-   加入者 (ユーザー) 番号。組織内のユーザーに割り当てることができます。

-   サービス番号 (有料またはフリーダイヤルのサービス番号) として利用できます。この番号は加入者番号よりも同時通話能力が高く、電話会議、自動応答、または通話キューなどのサービスに割り当てることができます。

これらの種類の電話番号の詳細については、「[プランの発信に使用されるさまざまな種類の電話番号](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)」を参照してください。

取得できる電話番号の合計数は、電話番号の種類と、ユーザーに購入して割り当てたライセンスの数によって異なります。

サービス番号については、電話会議の実装を慎重に計画する必要があります。 ビジネスで専用の電話会議電話番号が必要かどうかを評価します。許可されていない場合は、共有された電話会議の電話番号を使用することを組織が選ぶことができます。

取得できる電話番号の合計数については、「[取得できる電話番号](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)の数を確認する方法」を参照してください。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断のポイント|<ul><li>Microsoft から新しい電話番号を取得するユーザーの場所または事業所を決定します。</li><li>Microsoft から取得する電話番号の種類を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>Microsoft から新しい電話番号を取得するユーザーの場所またはオフィスを文書化します。</li><li>Microsoft から取得する電話番号の種類を文書化します。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>既存の電話番号を転送する

組織で既存の電話番号を Microsoft に転送 (またはポート) する場合は、Microsoft にポート注文の依頼を送信します。

既存のすべての電話番号を一度に転送できます。また、市場によっては、既存の電話番号のサブセット (部分的なポート) を転送することができます。 部分的なポートは、ダイヤルイン会議ブリッジを電話会議サービスに移動する場合に便利です。

1つのポート注文では、電話番号を1つの電話番号の種類にのみ転送できます。 一部の電話番号を加入者番号とサービス番号として転送する必要がある場合は、まず Microsoft への転送を完了し、Microsoft の制御範囲内にいるときはすぐに変換を実行することをお勧めします。

代わりに、部分的なポートがサポートされている場合は、一度に1つのポート要求を送信できます。 ただし、この別の方法を使用すると、既存の通信サービスプロバイダに契約が延長されます。

電話番号の移植は複雑なトピックであり、関係者の期待を綿密に計画、調整、適切に管理する必要があります。 詳細については、次の記事を参照してください。

-   [Office 365 への電話番号の移行](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [電話番号の移行に関するよくある質問](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断のポイント|<ul><li>既存の電話番号が Microsoft に移行されるユーザーの場所またはオフィスを決定します。</li><li>Microsoft に転送する電話番号の種類を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>既存の電話番号が Microsoft に移行されるユーザーの場所またはオフィスを文書化します。</li><li>Microsoft に転送される電話番号の種類を文書化します。</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>ダイヤル プラン

Office 365 の電話システム機能のダイヤルプランは、ダイヤルした電話番号を別の形式 (通常は164形式) に変換する正規化ルールのセットです。 電話会議サービスでは、電話システムで使用されているものと同じ機能を利用して、電話会議のダイヤルアウトシナリオで電話番号を翻訳します (たとえば、PSTN 経由で参加者を招待して、ダイヤルバックする、"通話する" 機能)。

Office 365 の電話システム機能には、2種類のダイヤルプランがあります。

-   **サービスダイヤルプラン:** これは、Office 365 の使用場所に基づいてユーザーに適用される既定のダイヤルプランであり、変更できません。

-   **テナントダイヤルプラン:** これはテナント内のカスタマイズ可能なダイヤルプランであり、さらに次の2つの種類に分かれています。

    -   **テナント-グローバルダイヤルプラン:** テナントのすべてのユーザーに適用されるダイヤルプラン。

    -   **テナント-ユーザーダイヤルプラン:** 特定のユーザーにのみ適用されるダイヤルプラン。

ユーザーに割り当てられている有効なダイヤルプランは、サービスダイヤルプラン (ユーザーの Office 365 の利用場所に基づく) とテナントダイヤルプラン (テナントグローバルダイヤルプランまたはテナントユーザーダイヤルプランのいずれか) を組み合わせたものです。

![サービスとテナントのダイヤルプランの3つの組み合わせを示す表](media/audio_conferencing_image8.png "サービスとテナントのダイヤルプランの3つの組み合わせを示す表")

> [!Important]
> 各テナントダイヤルプランには、最大25個の正規化ルールを適用できます。そのため、サービスのダイヤルプランの一部として既に利用可能な正規化ルールを重複しないようにすることが重要です。

ダイヤルプランの詳細については、「[ダイヤルプランとは](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)」を参照してください。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断のポイント|<ul><li>組織でカスタマイズされたダイヤルプラン (ビジネス要件、導入要件など) が必要かどうかを決定します。</li><li>必要に応じて、カスタマイズされたダイヤルプランの要件をサポートする、テナントダイヤルプラン (テナントグローバルまたはテナントユーザー) の範囲を決定します。</li><li>該当する場合は、クラウドボイスの実装の範囲内のユーザーの場所またはオフィスをサポートするために作成するテナントダイヤルプランを決定します。</li><li>必要に応じて、カスタマイズされたダイヤルプランを必要とするユーザーと、各ユーザーに割り当てるテナントダイヤルプランを決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>カスタマイズしたダイヤルプランと、関連付けられている正規化ルールを文書化して、クラウドボイスの実装の一部として構成します。</li><li>カスタマイズしたダイヤルプランを割り当てられるようにユーザーを指定し、各ユーザーに割り当てるテナントダイヤルプランを文書化します。</li></ul>|

> [!TIP]
> プロジェクトに該当する場合は、次のテンプレートを使用して、テナントダイヤルプランの構成を文書化することができます。
> 
> |テナントダイヤルプラン名<br>_説明_  |正規化ルール名<br>_説明_  |実線<br>変換<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_1つの Epping の道路ノース Ryde、NSW、AU Dial Plan_|**AU-NSW-NorthRyde-OER-Internal**<br>_Office、ノース Ryde、NSW、オーストラリアの1つの Epping 道路の内部番号 (x7000 x7999)_|^ (7 \ d{3}) $<br>+ 6125550 $ 1<br>True|
> ||**AU-NSW-ローカル**<br>_オーストラリア向けの市内番号の正規化 NSW_|^ ([2-9] \d{7}) $<br>+ 612 $ 1<br>False|
> ||**AU-TollFree**<br>_オーストラリア用のフリーダイヤル番号の正規化_|^ (1 [38] \d{4,8}) \d * $<br>+ 61 $ 1<br>False|
> ||**AU-サービス**<br>_オーストラリアのサービス番号の正規化_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-シンガポール-OMB**<br>_OMB シンガポール、SG ダイヤルプラン_|**SG-OMB-内部**<br>_OMB office、シンガポールの内部番号 (x8000)_|^ (8 \ d{3}) $<br>+ 656888 $ 1<br>True|
> ||**SG-TollFree**<br>_シンガポール向けのフリーダイヤル番号の正規化_|^ (1?800 \ d{7}) \d * $<br>+ 65 $ 1<br>False|
> ||**SG-サービス**<br>_シンガポール向けサービス番号の正規化_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>False|
> |**FR-CA-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-言語ライン Aux、フランスダイヤルプラン_|**FR-FR-39qdPR-内部**<br>_39 quai du Président Roosevelt office、Issy x7000-x7999 Lineaux、フランスの内部番号 ()_|^ (7 \ d{3}) $<br>+ 3319999 $ 1<br>True|
> ||**FR-FR-TollFree**<br>_フランス向けのフリーダイヤル番号の正規化_|^ 0? (80 \ d{7}) \d * $<br>+ 33 $ 1<br>False|
> ||**FR-CA**<br>_フランス向けのサービス番号の正規化_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10{2}\|\ d 3 \ d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> 以下のサンプルテンプレートを活用して、プロジェクトをサポートするためのダイヤルプランの割り当てを行うことができます。
>
> |ユーザー  |オフィス  |ダイヤルプランの種類  |ダイヤルプラン名  |
> |---------|---------|---------|---------|
> |Adele Vance|One Epping Road|テナントダイヤルプラン|AU-NSW-NorthRyde-OER|
> |Alex Wilber|One Epping Road|テナントダイヤルプラン|AU-NSW-NorthRyde-OER|
> |Ben Walters|One Epping Road|テナントダイヤルプラン|AU-NSW-NorthRyde-OER|
> |Christie Cline|One Marina Boulevard|テナントダイヤルプラン|SG-シンガポール-OMB|
> |Debra Berger|One Marina Boulevard|テナントダイヤルプラン|SG-シンガポール-OMB|
> |Lee Gu|One Marina Boulevard|テナントダイヤルプラン|SG-シンガポール-OMB|
> |Emily Braun|32 London Bridge Street|サービスダイヤルプラン|N/A|
> |Lidia Holloway|32 London Bridge Street|サービスダイヤルプラン|N/A|
> |ルイス Lahr|32 London Bridge Street|サービスダイヤルプラン|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|テナントダイヤルプラン|FR-CA-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|テナントダイヤルプラン|FR-CA-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|テナントダイヤルプラン|FR-CA-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>ドキュメントサービスの決定 

この記事の前のセクションの情報を使用して、サービスの決定を文書化してください。 一般的に、このドキュメントには次のメインセクションが含まれています。

-   電話会議サービスサイトの有効化リスト

-   電話会議の開催者のライセンス割り当てリスト

-   通信クレジットの計画番号

-   会議ブリッジの詳細

-   会議ブリッジの設定

-   電話会議ブリッジの設定の割り当て

-   電話番号購入プラン

-   テナントダイヤルプラン

-   ダイヤルプランの割り当て

<!--ENDOFSECTION-->