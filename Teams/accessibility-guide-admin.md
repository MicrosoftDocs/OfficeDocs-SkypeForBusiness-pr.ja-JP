---
title: Microsoft Teams 管理者向けのアクセシビリティ ガイド
ms.author: meghan
author: meganrmhan
ms.reviewer: eljones
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams のアクセシビリティを向上させるには、キャプションと文字起こしを有効にし、会議で手話インタープリターや CART キャプションへのアクセスを提供し、気を散らすのを減らし、参加を改善し、リソースを共有します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- M365-collaboration
ms.openlocfilehash: 7b089785695e9bef985107b5f1db8e5659c48c33
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614735"
---
# <a name="accessibility-guide-for-microsoft-teams-admins"></a>Microsoft Teams 管理者向けのアクセシビリティ ガイド

組織の Microsoft Teams 管理者は、すべてのユーザーに対して Teams 環境をできるだけ包括的でアクセスしやすいものにすることができます。 以下のガイドとリソースに従って、最適なアクセシビリティを実現するために Microsoft Teams を構成します。

> [!NOTE]
> アクセシビリティ オプションの多くは既定でオンになっていますが、このガイドの手順に従って無効になっていないことを確認できます。

## <a name="turn-on-captions-and-transcription-for-meetings-and-calls"></a>会議や通話のキャプションと文字起こしを有効にする

すべてのユーザーが参加して貢献できるように、包括的な会議を作成し、障腫のあるユーザーを呼び出します。

### <a name="turn-on-live-captions-for-meetings"></a>会議のライブ キャプションを有効にする

ライブ キャプションは、会議で言われる内容をリアルタイムで自動生成するテキストです。 ユーザーが有効にし、保存されていない場合は、一度に数行表示されます。

ユーザーのライブ キャプションを有効にするには:

1. Microsoft Teams 管理センターで、[ **会議**] に移動し、ドロップダウン会議 **ポリシー** を選択します。

2. 変更するポリシーを選択します。

3. **[参加者&ゲスト**] セクションに移動します。

4. **ライブ キャプションを** [無効] に切り替えます **が、ユーザーはオーバーライドできます**。

5. **[保存]** を選択します。

> [!TIP]
> [ユーザーが会議中にライブ キャプションを有効にする](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)方法を学習できるように、次のリンクを共有します。

> [!NOTE]
> ライブ キャプションは、コマーシャルおよび米国政府機関コミュニティ クラウド (GCC) 組織で開催される会議で利用できます。

### <a name="turn-on-transcription-for-calls"></a>呼び出しの文字起こしを有効にする

文字起こしは、呼び出しで言われた内容を自動的に生成して記録されたテキストです。 オンにすると、通話が終了した後にユーザーがトランスクリプトを確認できるようになります。

ユーザーの文字起こしを有効にするには:

1. Microsoft Teams 管理センターで **、Voice** に移動し、ドロップダウン [ **通話ポリシー**] を選択します。

2. 変更するポリシーを選択します。

3. **[文字起こし]** を **[オン]** にし、[保存] を選択 **します**。

### <a name="why-captions-and-transcripts-are-important"></a>キャプションとトランスクリプトが重要な理由

キャプションとトランスクリプトは、他のユーザーが話している単語のテキスト バージョンです。 ユーザーは、オーディオだけでなく、またはオーディオの代わりにテキストを表示するオプションをユーザーに提供します。 また、一部のユーザーが手話インタープリターまたは CART キャプションャーから受け取る内容に関する追加情報を提供することで、聴覚障碍や聴覚障碍のある人にも役立ちます。

キャプションと文字起こしは、さまざまな状況で役立ちますが、特に次の場合に役立ちます。

- 聴覚障碍者または聴覚障碍者People

- 学習障 People

- People、会議が終了した後に共有された情報を確認する必要がある、または気が散る環境にいるユーザー

詳細については、次のリンクを参照してください。

- [記録と文字起こしの会議ポリシー設定](/Microsoftteams/meetings-policies-recording-and-transcription)

- [Web コンテンツ アクセシビリティ ガイドライン (WCAG) 1.2.4.: キャプション (Live)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

## <a name="give-meeting-access-to-sign-language-interpreters-and-cart-communication-access-real-time-translation-captioners"></a>会議で手話インタープリターと CART (Communication Access リアルタイム翻訳) のキャプションにアクセス権を付与する

手話インタープリターと CART (コミュニケーション アクセスリアルタイム翻訳) キャプション作成者に Microsoft Teams 会議へのアクセス権を付与し、聴覚障碍のあるユーザーとより効果的に連携できるようにします。

### <a name="admit-sign-language-interpreters-and-cart-captioners-to-meetings"></a>会議に手話インタープリターと CART キャプションを許可する

サインイン言語インタープリターと CART キャプションは組織では機能しない可能性がありますが、 [ゲスト アクセス権を付与することで](/MicrosoftTeams/guest-access) Microsoft Teams 会議に招待できます。

ゲスト アクセスが付与されたら、手話インタープリターと CART キャプションを会議に許可します。

1. Microsoft Teams 管理センターで、[ **会議**] に移動し、ドロップダウン会議 **ポリシー** を選択します。

2. 変更するポリシーを選択します。

3. **[参加者&ゲスト**] セクションに移動します。

4. [組織のコンプライアンスとセキュリティ要件に最も適した **ユーザーを自動的に許可** する] のオプションを選択します。 次のいずれかのオプションを選択できます。

   - すべてのユーザー (推奨されません)

   - 組織内のPeopleとゲスト (推奨)

   - 自分の組織、信頼できる組織、およびゲストのユーザー

   - 自分の組織のユーザー

   - 開催者のみ

   - 招待されたユーザーのみ

5. **[保存]** を選択します。

> [!NOTE]
> [ **ユーザーを自動的に許可** する] 設定は、ダイヤルイン ユーザーには適用されません。

### <a name="turn-on-ip-video-feed-for-your-users"></a>ユーザーの IP ビデオ フィードを有効にする

Microsoft Teams 会議中に、聴覚障碍のあるユーザーと通信できるように、手話インタープリターに IP ビデオ フィードを共有する機能を提供します。

IP ビデオ フィードがオンになっているかどうかを確認するには:

1. Microsoft Teams 管理センターで、[ **会議**] に移動し、ドロップダウン会議 **ポリシー** を選択します。

2. 変更するポリシーを選択します。

3. **[オーディオ & ビデオ**] セクションに移動します。

4. **IP ビデオ** が **オン** になっていることを確認し、[保存] を選択 **します**。

> [!TIP]
> 次のリンクをユーザーと共有して、Teams を使用して会議に参加、集中、共同作業する能力を最大限に高める方法を調整できるようにします。
> - [会議ビューをカスタマイズする](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)
> - [CART キャプションを使用する](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

### <a name="why-its-important-to-include-sign-language-interpreters-and-cart-captioners"></a>手話インタープリターと CART キャプションを含めるのが重要な理由

一部のユーザーは、自動生成されたキャプションよりも特定の専門用語、アクセントなどについてより正確な場合があるため、CART キャプションを使用することをお勧めします。

主なコミュニケーション方法が手話であるユーザーは、手話の解釈を必要とします。これには、人間のインタープリターが存在する必要があります。

詳細については、「 [Web コンテンツ アクセシビリティ ガイド (WCAG) 1.2.6.: 手話の解釈](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)」を参照してください。

## <a name="reduce-distractions-in-meetings"></a>会議で気を散らすのを減らす

Teams 会議で気を散らすのを減らすためにビデオ フィルターをオンにすることで、ユーザーの参加を促します。

### <a name="turn-on-video-filters"></a>ビデオ フィルターを有効にする

ビデオ フィルターは、会議中の邪魔を減らすのに役立ちます。

ビデオ フィルターを有効にするには:

1. Microsoft Teams 管理センターで、[ **会議**] に移動し、ドロップダウン会議 **ポリシー** を選択します。

2. 変更するポリシーを選択します。

3. **[コンテンツ共有**] セクションに移動します。

4. [組織のコンプライアンスとセキュリティの要件に最も適した **ビデオ フィルターを選択する]** でオプションを選択します。 次のいずれかのオプションを選択します。

   - 背景のぼかしのみ

   - 背景のぼかしと既定の画像

   - すべてのフィルター

5. **[保存]** を選択します。

> [!TIP]
> ユーザーが Teams 会議の設定を調整して気を散らさないようにするには、次のリンクを共有します。
> - [Teams 会議の背景効果を変更する](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)
> - [Teams 会議のバックグラウンド ノイズを減らす](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

### <a name="why-its-helpful-to-reduce-distractions"></a>気を散らすのを減らすのに役立つ理由

組織内の一部のユーザーは、参加者の背景に動き、軽い、その他の気を散らすため、ビデオ会議や通話中に集中するのが難しい場合があります。 ビデオ フィルターを使用すると、ユーザーは気を散らしたり、完全に参加したりするのに役立ちます。

*背景効果* は、話者の背景ではなく、話者に焦点を当てるのに役立ちます。 Microsoft Teams にはバックグラウンドのライブラリがあり、ユーザーは自分でアップロードすることもできます。

*背景のぼかし* は、会議や通話時の可視性とフォーカスを向上するのに役立ちます。これは、バックグラウンドでの気晴らしを減らしますが、ユーザーはフォーカスを維持するためです。

ビデオ フィルターは、さまざまな状況で役立ちますが、特に次の場合に役立ちます。

- ニューロディバのPeople

- 聴覚障碍者または聴覚障碍者People

詳細については、「 [Web コンテンツ アクセシビリティ ガイドライン (WCAG) 1.4.8.: Visual Presentation](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)」を参照してください。

## <a name="improve-participation-in-microsoft-teams-meetings"></a>Microsoft Teams 会議への参加を改善する

**会議でチャット** を有効にし、チャットの編集、イマーシブ リーダー、絵文字などのメッセージング ポリシーを有効にすることで、制御と柔軟性に関するより多くのオプションを使用 **して**、ユーザーの参加を促します。

### <a name="turn-on-chat-in-meetings"></a>会議でチャットを有効にする

チャットを使用すると、多くのユーザーが Teams 会議で質問したり、情報を追加したりしやすくなります。

会議内チャットが有効になっているかどうかを確認するには:

1. Microsoft Teams 管理センターで、[ **会議**] に移動し、ドロップダウン会議 **ポリシー** を選択します。

2. 変更するポリシーを選択します。

3. **[参加者&ゲスト**] セクションに移動します。

4. [ **会議のチャット] で** 、組織のコンプライアンスとセキュリティ要件に最も適したオプションを選択します。 次のいずれかのオプションを選択できます。

   - すべてのユーザーに対して有効にする (推奨)

   - すべてのユーザーに対してオフにする (推奨されません)

   - 匿名ユーザー以外のすべてのユーザーに対して有効にする

5. **[保存]** を選択します。

### <a name="use-messaging-policies-for-increased-flexibility-and-control"></a>メッセージング ポリシーを使用して柔軟性と制御を向上させる

柔軟なチャット オプションを使用すると、多くのユーザーが他のユーザーのメッセージを理解し、自分のメッセージを修正し、自分自身を表現しやすくなります。

これらの柔軟なチャット オプションが有効になっているかどうかを確認するには:

**Microsoft Teams 管理センター** で、次の手順を実行します。

1. Microsoft Teams 管理センターで、 **メッセージング ポリシー** に移動します。

2. 変更するポリシーを選択します。

3. 次の項目が **オン** になっていることを確認します。

   - **送信済みメッセージを削除する**

   - **送信済みメッセージを編集する**

   - **チャット**

   - **会話の Giphys**

   - **会話中のミーム**

   - **会話のステッカー**

   - **URL プレビュー**

   - **メッセージを翻訳する**

   - **メッセージのイマーシブ リーダー**

4. **[保存]** を選択します。

> [!TIP]
> チャットで共有されるテキスト以外のメッセージをユーザーが理解できるように、 [効果的な代替テキストを組織に書き込む方法](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2) をリンクで共有します。

### <a name="why-alternate-participation-options-matter"></a>代替参加オプションが重要な理由

柔軟なチャット オプションを使用すると、ユーザーは会議内チャット コンテンツを使用する方法の柔軟性が向上し、チャットを使用して会議に参加する方法をより細かく制御できます。

*会議内チャットでは、* 会議のディスカッションに参加する別の方法がユーザーに提供されます。 障舟者の場合は、話し合いに貢献する方法として、音声または手話をする方がチャットが望ましい場合があります。

*イマーシブ リーダー* は、難読症や難読症を持つ人向けに設計されたツールで、テキストを理解しやすくするのに役立ちます。 また、別の言語でのコミュニケーションを好むユーザー向けのインライン翻訳も含まれています。 イマーシブ リーダーの主な機能の一部は次のとおりです。

- コンテンツを読み上げるオプションを追加する

- テキスト サイズと背景色の変更

- 単語を音節に分割する

- 文字間のスペースを増やす

- 1 行以上のテキストを強調表示する

- 音声の一部を強調表示する

柔軟なチャット オプションは、さまざまな状況で役立ちますが、特に次の場合に役立ちます。

- 視覚障碍者または視覚障碍のあるPeople

- ニューロディバエであるPeople (つまり、失読症またはジスグラフ症を持つ)

詳細については、「 [Web コンテンツ アクセシビリティ ガイドライン (WCAG) 1.1.1.: 代替テキスト](https://www.w3.org/TR/WCAG21/#text-alternatives)」を参照してください。

## <a name="share-resources-with-users-to-further-accessibility-awareness"></a>ユーザーとリソースを共有してアクセシビリティを向上させる

アクセシビリティのエクスペリエンスを向上させるために、ユーザーが実行できる追加の手順があります。 以下のリンクを組織やゲスト ユーザーと共有します。

### <a name="reference-links"></a>リファレンス リンク

Microsoft の Disability Answer Desk には、アクセシビリティのニーズに合わせてエクスペリエンスをカスタマイズするためのエンド ユーザー ガイドがあります。

- [会議中にライブ キャプションを有効にする](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)

- [会議ビューをカスタマイズする](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)

- [CART キャプションを使用する](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

- [Teams 会議の背景効果を変更する](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)

- [Teams 会議のバックグラウンド ノイズを減らす](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

- [有効な代替テキストを書き込む](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2)

- [Microsoft Teams のアクセシビリティ ツール](https://support.microsoft.com/office/accessibility-tools-for-microsoft-teams-2d4009e7-1300-4766-87e8-7a217496c3d5?ui=en-us&rs=en-us&ad=us)

### <a name="reference-web-content-accessibility-guidelines-wcag"></a>Web コンテンツアクセシビリティガイドライン (WCAG) を参照する

WCAG は、Web アクセシビリティを向上させるために設計された一連の国際標準です。 このガイドで参照されている成功基準は次のとおりです。

- [WCAG 1.2.4.: キャプション (Live)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

- [WCAG 1.2.6.: 手話の解釈](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)

- [WCAG 1.4.8.: Visual Presentation](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)

- [WCAG 1.1.1.: 代替テキスト](https://www.w3.org/TR/WCAG21/#text-alternatives)
