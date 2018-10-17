---
title: 決定を下すオーディオ会議サービス - マイクロソフトのチーム
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 会議、ライセンスと可用性については、会議ブリッジの設定を構成する、取得または電話番号を転送し、テナントを選択するダイヤル プランです。
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81dca894a378c5331c34b5840108e63536c8ac37
ms.sourcegitcommit: f76497a93dc3382c0ff2fc115c8f3e704097ab5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2018
ms.locfileid: "25597839"
---
# <a name="make-my-service-decisions"></a>[サービスの決定を行う

オーディオ会議の技術的な実装を計画するには、一連のより適切に定義されたビジネス要件を満たすソリューションを実装する組織を準備するのには事前にサービスの判断を行う必要があります。

## <a name="audio-conferencing-in-teams"></a>チームでの音声会議

マイクロソフトのチームで必要な電話会議機能を定義することの一環として、公開最新のロードマップの決定を評価する最初の手順のいずれかです。

-   スコープ内のユーザーに対して展開されるチームの電話会議機能。

-   チームで電話会議の機能の要件をユーザーが必要です。

-   最新のパブリック ・ ロードマップに記載されているチームでの音声会議機能が、ユーザー、機能、および展開の時間内で、スコープの要件を満たすことを確認します。

> [!NOTE]
> 展開があるは、スコープ内のチームの電話会議機能を識別するための最新のチーム ロードマップ<https://aka.ms/skype2teamsroadmap>。

## <a name="meetings-in-teams"></a>Teams での会議

チームは、スケジュール、HD ビデオを使用してオンライン会議に参加し、IP (VoIP)、および PSTN ダイヤルイン会議のオプションの音声機能をユーザーに与えます。

秘密の会議 (招待者のみが参加できます) として会議をスケジュールすることができます。 またはチャネル会議のために開いているチャネルへのアクセスを持つすべてのユーザー)、ユーザーでは、チャネル内での緊急の会議を開始できますもします。

> [!NOTE]
> チーム内の会議の機能の詳細については、[Microsoft チーム機能のロードマップにビジネスの Skype] を参照してください。 https://aka.ms/skype2teamsroadmap)。

ミーティングの参加者を有料または無料のダイヤルイン会議ブリッジ landlines または携帯電話の電話番号にダイヤルすることによって、チームの会議に参加できます。 (データ接続が信頼性の高いされていないときに便利です)、その電話を呼び出し、会議ブリッジまたは使用すると、会議で会議に参加できるように、「電話」機能を開始するオーディオ会議サービスをさせることができますさらに、開催者が会議に招待その電話をダイヤルすることによって参加者です。

> [!IMPORTANT]
> チームでの音声会議には、サード ・ パーティ製の音声会議プロバイダー (Acp) をサポートしていません。

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>電話会議の利用可否

チームでのオーディオ会議の実装を計画する前に、[オーディオ会議や予定を呼び出すための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)の詳細と、オーディオ会議サービスの可用性を確認する必要があります。

> [!IMPORTANT]
> 多国籍組織では、使用できるオーディオ会議のための法的な制約のための国や地域がオーディオ会議サービスは、商業的に利用可能な場所から Office 365 サブスクリプションの契約を供給する必要があります。

組織が対象となることを確認した後はオーディオ会議サービスを取得するには、ユーザーの所在地、またはオフィスの電話会議サービスを実装するのリストをコンパイルに基づいて使用可能な国や地域の一覧です。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>電話会議サービスを実装するユーザーの場所またはオフィスを決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>電話会議サービスを有効にするユーザーの場所とオフィスを文書化します。</li></ul>|

> [!TIP]
> オーディオ会議サイト対応のリスト テンプレートの例を以下に示します。
> 
> |オフィス   |場所 |PSTN 会議サービス  |
> |---------|---------|---------|
> |One Epping Road|オーストラリア|電話会議|
> |100 Cyberport Road|香港特別自治区|旧 PSTN 会議|
> |One Marina Boulevard|シンガポール|電話会議|
> |32 London Bridge Street|イギリス|電話会議|
> |39 quai du Président Roosevelt|フランス|電話会議|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>電話会議のライセンス

[オーディオ会議のライセンス](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)は、Office 365 の E5 のサブスクリプションの計画の一環として、または Office 365 の E1 または Office 365 の E3 のサブスクリプションの計画に追加サービスとして利用できます。

> [!NOTE]
> チームで、PSTN またはダイヤルイン会議では、サード ・ パーティ製の音声会議プロバイダー (Acp) をサポートしていません。
> <br>Skype for Business Online PSTN 会議を使用している場合は、Teams ですぐに電話会議を利用できます。

無料電話会議ブリッジの電話番号を指定して、会議の国際電話番号にダイアル アウトをサポートするためには、組織の[通信のクレジット](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)を設定する必要があります。

> [!IMPORTANT]
> 一部の国は無料電話会議ブリッジの電話番号のみでサービスを提供します。 サポートするためにダイヤルすることでこれらの国で通信のクレジットを使用する必要があります。

購入する資金の初期量を決定する必要が通信のクレジットを実装するときに最初の考慮点です。 組織は、自動リチャージを使用するが場合、トリガー (金の最低金額) と自動充電量を決定する必要があります。 実際の使用状況は、自動リチャージ金額を決定します。 時間の経過とともに、通信のクレジットの使用状況を監視し、必要に応じて再充電量を調整する必要があります。

通信のクレジットに関する詳細については、[ここで](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>組織では、ライセンス、必要なオーディオ会議を既に購入していない場合、によって既存の Office 365 サブスクリプションをステップ実行、またはオーディオ会議アドオン ・ ライセンスを入手することで、オーディオ会議のライセンスを習得していただくことがあるかどうかを決定します。</li><li>通信のクレジットは、電話会議を実装するために必要かどうかを決定します。 必要な場合は、初回購入金額を決定します。 該当する場合は、リチャージを実行する金額と自動リチャージする金額を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>オーディオ会議のライセンスを割り当てられるユーザーを文書化します。</li><li>(初期金額、トリガーの量、自動リチャージ金額) は、通信のクレジット計画を文書化します。</li></ul>|

> [!TIP]
> 次の例を使用してオーディオ会議のユーザーのライセンスの割り当ての一覧を文書化できます。
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
> |ルイ Lahr|32 London Bridge Street|Office 365 E5|
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

-   会議の複数の種類のブリッジの電話番号 (有料および無料)

-   会議ブリッジの複数のカテゴリの電話番号 (専用および共有)

-   会議ブリッジでの複数言語のサポート (プライマリとセカンダリ)

-   テナントのための既定の電話番号

> [!NOTE]
> 該当するライセンスの数に基づいて、テナントごとに取得できる電話番号の中に専用の会議ブリッジ電話番号カウントします。 無料電話の会議ブリッジ電話番号では通信クレジットが必要になります。

かどうかは、オーディオ会議サービスを既存の会議ブリッジの電話番号を転送する必要があります-国に固有の要件を満たしていると仮定した場合、これら既存の会議ブリッジの電話番号をマイクロソフトに転送することができます。

> [!NOTE]
> マイクロソフトに電話番号を転送するの複雑さは、国または地域、運送会社、関連する回路の数、多くの他の要因によって大きく異なります。 これは、事前処理を開始するためにする可能性がどのくらいの期間を調査するのには、現在のプロバイダーを使用してタイムラインを満たすために十分な。

会議ブリッジの電話番号の詳細については、以下の資料を確認してください。

-   [Skype for Business および Microsoft Teams の電話会議のセットアップ](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [電話会議の電話番号](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [サービスの電話番号の取得](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [Office 365 に電話番号を移行する](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>専用会議ブリッジの電話番号が組織に必要があるかどうかを決定します。</li><li>ユーザーの所在地、またはオフィスの専用会議ブリッジの電話番号を取得する方法を決定する (つまりは、マイクロソフトまたは転送の既存の電話番号から取得) オーディオ会議の実装の範囲内です。</li><li>マイクロソフトから入手する方法を選択する場合に使用する方法を決定 (フォーム送信または自動) のユーザーの場所やオフィスの範囲内のオーディオ会議の実装。</li><li>各専用ブリッジ電話会議の番号を設定する言語を決定します。</li><li>テナント既定会議ブリッジの電話番号を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>各ユーザーの場所や電話会議の実装のスコープ内のオフィスの電話番号を取得する方法の詳細を示す電話番号の取得のマスター プランを文書化します。</li><li>該当する場合、新しい電話番号を要求フォームを完了する、場所やオフィスごとに 1 つのフォームです。</li><li>詳細な会議ブリッジ電話番号の構成 (共有、専用の会議ブリッジの電話番号、各専用ブリッジ電話会議の番号、テナント既定会議ブリッジの電話番号の優先言語の設定) を文書化します。</li></ul>|

会議ブリッジの詳細情報をキャプチャすることができますを使用するテンプレートの例を次に示します。

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

ユーザー エクスペリエンスをさらに調整するには、オーディオ会議の会議 (会議の開始と終了を通知し、呼び出し元名の記録)、会議の開催者の暗証番号 (pin) の長さ、および電子メールの通知に参加するための組織全体のオプションを設定します。

-   会議の参加と退出に関する通知は、記録された名前、電話番号、効果音の形式で利用できます。

-   PIN の長さは 4～12 桁です。既定は 5 桁の PIN です。

-   オーディオ会議のライセンスまたはその他の管理者による変更の対応に送信された電子メールが既定で有効に通知します。 この機能を無効にし、組織のユーザーの通信を制御できます。

オーディオ会議のライセンスが割り当てられているユーザーの場合は、使用するデフォルト有料/toll フリー番号、電話会議の座標に示すようを構成できます。

-   テナント レベルのデフォルトです。

-   自動的に割り当てられている会議ブリッジの電話番号です。

-   ユーザーごとに手動で構成、会議ブリッジの電話番号です。

ユーザー固有の会議では、電話の番号は、通常は、グローバルまたは全国的な組織ではユーザーが配布され、その会議出席依頼で既定の会議ブリッジの電話番号とローカル番号を提供する必要がありますをブリッジします。

参加者が別の都市や海外への参加は、テナント ・ レベルで構成されているその他の番号を検索できますが、会議出席依頼に直接これらの番号が表示されません。 会議出席依頼は、**チーム会議にダイヤルイン番号**のページにその場所に最も近い会議ブリッジの電話番号を検索するには、参加者のリンクを提供します。

呼び出し元の認証方法を構成することもそれぞれ個別の会議の開催者によって処理される、認証されていない呼び出し元の入場が許可されること、または、許可する前に、会議を開始するのには会議の開催者を必要とするかどうか、会議を開始する呼び出し元が認証されていません。.

フリー ダイヤル会議ブリッジの電話番号の使用を制御し、会議からダイヤルアウトするには、各ユーザーの追加の構成を適用することもできます。

> [!NOTE]
> 現時点では、料金に関連するこれらの制御はプレビュー カスタマーのみが利用できます。 プレビュー プログラムに組織を登録することができますhttps://www.skypepreview.com。

これらのコントロールでは、ミーティングの開催者が、それらが開催する会議の無料電話会議ブリッジの電話番号を提供するかどうかと、参加者が会議の主催者から発信かどうかを決定できます。 ダイアル アウト制御のレベルにまたがるからのみ、国内および海外の番号にダイヤルアウトを許可するのには、国内の番号にダイヤルアウトを許可する、ダイヤルを完全に防止します。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>組織に、開始と終了の通知が必要かどうかを決定して -存在する場合は-を実装する通知の種類 (音、電話番号、または記録されている名前)。</li><li>組織のセキュリティ要件を満たすオーディオ会議の暗証番号 (pin) の長さを決定します。</li><li>組織がオーディオ会議サービスに関連するユーザーの通信を制御するかどうかを決定します。</li><li>会議ブリッジ電話番号を各会議の開催者に割り当てるかどうかを決定します。</li><li>無料電話会議ブリッジの電話番号を使用して、その会議にミーティング開催者が必要かどうかを決定します。</li><li>会議開催者が会議を開始するのには認証されていない呼び出し元を許可する必要があるかどうかを決定します。</li><li>いくつかの会議の開催者が会議のダイヤル ・ アウトを制御する必要があるかどうかを決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>詳細な会議ブリッジ設定 (参加および退出の通知、PIN 長さ、構成変更メール通知) を文書化します。</li><li>各会議の開催者と、認証されていない呼び出し元のポリシーを制御するための対応する設定に割り当てられているし、フリー ダイヤル会議ブリッジの電話番号を文書化し、コントロールをダイヤルします。</li></ul>|

> [!TIP]
> 次の例のように、会議ブリッジの設定を文書化することができます。
> 
> |         |         |
> |---------|---------|
> |会議の参加および退出の通知を有効にする|有効|
> |参加/退出のアナウンスのタイプ|効果音|
> |会議に参加する前に名前を記録するように発信者に求める|無効|
> |PIN の長さ|5|
> |ユーザーのダイヤルイン設定の変更時にそのユーザーに自動的にメールを送信する|無効|

<br>

> [!TIP]
> 次の例を使用してオーディオ会議のユーザーに対して会議ブリッジの設定の割り当ての一覧を文書化できます。
>
> |ユーザー  |オフィス  |既定の有料電話番号  |既定の無料電話番号  |無料電話を許可する  |未認証の発信者のバイパス ロビー  |会議ダイヤルアウト  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|One Epping Road|TBA|TBA|はい|有効|国際および国内|
> |Alex Wilber|One Epping Road|TBA|TBA|いいえ|無効|許可されていない|
> |Ben Walters|One Epping Road|TBA|TBA|いいえ|無効|許可されていない|
> |Christie Cline|One Marina Boulevard|TBA|TBA|はい|無効|国内|
> |Debra Berger|One Marina Boulevard|TBA|TBA|はい|有効|国内|
> |Lee Gu|One Marina Boulevard|TBA|TBA|はい|有効|国内|
> |Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|はい|有効|許可されていない|
> |Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|はい|無効|許可されていない|
> |ルイ Lahr|32 London Bridge Street|+44 20 7946 0001|TBA|はい|無効|許可されていない|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|いいえ|無効|国内|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|はい|有効|国際および国内|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|いいえ|無効|国内|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>クラウド音声電話番号を管理します。

会議のオーディオ実装では、新しい電話番号を取得するか、既存の電話番号とポートを転送することができます。

慣れている方法を電話番号にダイヤルできるようにするのには-をダイヤルする市内通話、市外局番を省略することの国内通話は、国コードを省略することまたは短い数字の会議を実行するときのダイヤルを使用した場合でも、カスタマイズされたダイヤル プランを構成することができますユーザーに割り当てます。

## <a name="acquire-new-telephone-numbers"></a>新しい電話番号を取得します。

マイクロソフト クラウド音声ソリューション内の電話番号の 2 つの種類は次のとおりです。

-   サブスクライバー (ユーザー) 番号は、組織内のユーザーに割り当てることができます。

-   サービス番号、有料電話番号と加入者番号よりも高いの同時呼び出し容量があり、オーディオ会議、自動応答、またはキューの呼び出しなどのサービスに割り当てることができるサービスのフリー ダイヤル番号として使用します。

これらの種類の電話番号の詳細については、[さまざまな種類](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)を参照してください。

取得できる番号は、電話番号の種類とライセンスの数によって異なります。 電話の合計数を購入して、ユーザーに割り当てられています。

サービス番号に関しては、慎重に、オーディオ会議の実装を計画する必要があります。 ビジネス専用会議ブリッジの電話番号にする必要があるかどうかを評価します。それ以外の場合は、共有会議ブリッジの電話番号を使用する組織を選択できます。

取得できる電話番号の合計数の詳細についてを参照してください[電話番号の数を取得することができますか?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>ユーザーの場所やオフィスがマイクロソフトから新しい電話番号を取得する場所を決定します。</li><li>Microsoft から取得する電話番号の種類を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>ユーザーの所在地、またはマイクロソフトから新しい電話番号を取得する場所のオフィスを文書化します。</li><li>Microsoft から取得する電話番号の種類を文書化します。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>既存の電話番号を転送します。

組織は、既存の電話番号をマイクロソフトに転送 (またはポート) する必要がある場合これを行うマイクロソフトにポートの注文要求を送信することで。

すべての既存の電話番号を一度に (全ポート) を転送することができますと、一部の市場で、既存の電話番号 (一部のポート) のサブセットを転送することができます。 部分のポートにだけ必要がある場合、ダイヤルイン会議ブリッジをオーディオ会議サービスに移動することができます。

1 つのポートの順序は、1 つの電話番号の種類に電話番号を転送することができますだけです。 加入者番号と、電話の番号の一部といくつかのサービスの番号に転送する必要があります、マイクロソフトへの転送を完了し、マイクロソフトのコントロール内では、すぐに変換を実行することをお勧めします。

代わりに、一部のポートがサポートされている場合を送信できます複数のポートの要求、要求の 1 つのポートで。 ただし、この方法は、既存の通信サービスのプロバイダーとの契約内容が延長されます。

電話番号を移植して、複雑なトピックでは、綿密な計画、調整、および利害関係者の期待を適切に管理する必要があります。 詳細については、以下の資料を参照してください。

-   [Office 365 に電話番号を転送します。](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [電話番号の移行に関するよくある質問](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>ユーザーの所在地、またはオフィスの既存の電話番号をマイクロソフトに転送されますを決定します。</li><li>マイクロソフトに転送する電話番号の種類を決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>文書化するには、ユーザーの所在地、またはオフィスの既存の電話番号をマイクロソフトに転送されます。</li><li>マイクロソフトに転送する電話番号の種類を文書化します。</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>ダイヤル プラン

Office 365 の電話システムの機能で、ダイヤル プランでは、正規化の規則のセットに変換する他の形式 (通常は E.164 形式) に承認し、通話のルーティングの電話番号をダイヤルします。 オーディオ会議サービスでは、会議ダイヤルアウト用のシナリオ (たとえば、参加者を招待 PSTN とダイヤル バックでは、「電話」機能を使用して) でダイヤルされた電話番号を変換するために、電話システムで使用されるのと同じ機能を活用します。

Office 365 の電話システムの機能では、ダイヤル プランの 2 種類があります。

-   **サービスのダイヤル プラン:** これは、既定の Office 365 の使用状況の場所に基づいて、ユーザーに適用されているダイヤル プランと、変更することはできません。

-   **のテナントのダイヤル プラン:** これは、さらに次の 2 種類に分かれているテナント内のカスタマイズ可能なダイヤル プランです。

    -   **テナント グローバル ダイヤル プラン:** テナント内のすべてのユーザーに適用されるダイヤル プランです。

    -   **テナント ユーザー ダイヤル プラン:** ダイヤル プランを特定のユーザーだけに適用されます。

ユーザーに割り当てられている有効なダイヤル プラン (ユーザーの Office 365 の使用状況の場所に基づく) サービスのダイヤル プランの組み合わせは、テナントのダイヤル プラン (テナント グローバル ダイヤル プランまたはテナントのユーザーのダイヤル プランのいずれかであることができます)。

![テーブルは、サービス、テナントの組み合わせを次の 3 つのダイヤル プランを示しています]。(media/audio_conferencing_image8.png "テーブルは、サービス、テナントの組み合わせを次の 3 つのダイヤル プランを示しています")。

> [!Important]
> あります最大 25 の正規化ルールでは、各テナントのダイヤル プランです。したがってが使用されている正規化ルールと重複しないようにするのには重要なサービスの一部としてダイヤル プランです。

ダイヤル プランの詳細についてを参照してください[のダイヤル プランは何ですか?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>組織にカスタマイズされたダイヤル プランが (ビジネス要件、導入要件、およびなど) が必要かどうかを決定します。</li><li>該当する場合は、カスタマイズしたダイヤル プランの要件を満たすテナント ダイヤル プランの範囲 (テナント - グローバルまたはテナント - ユーザー) を決定します。</li><li>該当する場合、テナントのダイヤル プランがユーザーの所在地、またはオフィスをサポートするために作成することを決定するクラウドのボイスの実装の範囲内です。</li><li>該当する場合、カスタマイズされたダイヤル プランとテナントのダイヤル プランの各ユーザーに割り当てられるユーザーが必要なを決定します。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>クラウド ボイス実装の一部として構成するには、カスタマイズされたダイヤル プランと関連付けられた正規化ルールを文書化します。</li><li>カスタマイズされたダイヤル プランとユーザーごとに割り当てられるテナントのダイヤル プランに割り当てられるユーザーを文書化します。</li></ul>|

> [!TIP]
> プロジェクトに適用可能な場合は、テナントのダイヤル プランの設定を文書化するのには次のテンプレートを使用できます。
> 
> |テナント ダイヤル プランの名前<br>_説明_  |正規化ルールの名前<br>_説明_  |パターン<br>変換<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde、NSW、AU ダイヤル プラン_|**AU-NSW-NorthRyde-OER-Internal**<br>_One Epping Road オフィスの内部番号 (x7000 - x7999)、North Ryde、NSW、オーストラリア_|^(7\d{3})$<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_NSW、オーストラリアの市内番号の正規化_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_オーストラリアの無料電話番号の正規化_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
> ||**AU-Service**<br>_オーストラリアのサービス番号の正規化_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapore、SG ダイヤル プラン_|**SG-OMB-Internal**<br>_行政管理予算局のオフィス、シンガポールの内部番号 (x8000-経費"x 8999)_|^(8\d{3})$<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_シンガポールの無料電話番号の正規化_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
> ||**SG-Service**<br>_シンガポールのサービス番号の正規化_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux、フランスのダイヤル プラン_|**FR-39qdPR-Internal**<br>_39 quai du Président ルーズベルトのオフィス、Issy の内部番号 ("x-7999 x7000-経費)-ゴ-Moulineaux (フランス)_|^(7\d{3})$<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_フランスの無料電話番号の正規化_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
> ||**FR-Service**<br>_フランスのサービス番号の正規化_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

<br>
> [!TIP]
> 次のテンプレートの例を利用して、ダイヤル プランを文書化してプロジェクトをサポートすることができます。
>
> |ユーザー  |オフィス  |ダイヤル プランの種類  |ダイヤル プランの名前  |
> |---------|---------|---------|---------|
> |Adele Vance|One Epping Road|テナント ダイヤル プラン|AU-NSW-NorthRyde-OER|
> |Alex Wilber|One Epping Road|テナント ダイヤル プラン|AU-NSW-NorthRyde-OER|
> |Ben Walters|One Epping Road|テナント ダイヤル プラン|AU-NSW-NorthRyde-OER|
> |Christie Cline|One Marina Boulevard|テナント ダイヤル プラン|SG-Singapore-OMB|
> |Debra Berger|One Marina Boulevard|テナント ダイヤル プラン|SG-Singapore-OMB|
> |Lee Gu|One Marina Boulevard|テナント ダイヤル プラン|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|サービス ダイヤル プラン|該当なし|
> |Lidia Holloway|32 London Bridge Street|サービス ダイヤル プラン|該当なし|
> |ルイ Lahr|32 London Bridge Street|サービス ダイヤル プラン|該当なし|
> |Marcel Beauchamp|39 quai du Président Roosevelt|テナント ダイヤル プラン|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|テナント ダイヤル プラン|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|テナント ダイヤル プラン|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>ドキュメント サービスに関する意思決定 

この資料の前のセクションからの情報を使用して、決定事項をサービスします。 一般に、このドキュメントは次の主要なセクションに含まれます。

-   電話会議サービス サイト有効化リスト

-   電話会議の開催者のライセンス割り当てリスト

-   通信クレジットの計画番号

-   会議ブリッジの詳細

-   会議ブリッジの設定

-   会議ブリッジの設定の割り当て

-   電話番号を買収

-   テナント ダイヤル プラン

-   ダイヤル プランの割り当て

<!--ENDOFSECTION-->