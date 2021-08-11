---
title: '[通話の評価] Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '概要: [通話の評価] 機能について、Skype for Business Server。'
ms.openlocfilehash: 6623729dced8128e010ac0a61dfd2fccd95f1c558deda1342b0db92936f0b31f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326433"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>[通話の評価] Skype for Business Server

**概要:** 詳細については、「通話料金」の機能Skype for Business Server。

Rate My Call は、Skype for Business Windows の Skype for Business および 2016 クライアントの新機能であり、企業はエンド ユーザーからフィードバックを受け取る方法を提供します。

[通話のレート] ウィンドウには、"スター" 評価システムと、音声通話とビデオ通話用の定義済みトークンが用意されています。 さらに、管理者はユーザー設定フィールドを有効にしてフィードバックを提供できます。

収集されたレートの自分の通話データは、現在、既存の監視レポートには含まれていませんが、個別の監視レポートがあります。 データは、クエリSQL実行してアクセスできるテーブルSQLされます。

## <a name="rate-my-call-prerequisites"></a>通話の前提条件を評価する

アプリの展開のユーザー Skype for Business Server、Rate My Call 機能にアクセスするには、次のコンポーネントセットを展開して構成する必要があります。

-  インストールされている必要Skype for Business Server (バージョン 9160 以上)。

- ユーザーに最新バージョンのアプリをインストールして更新Skype for Business UI を使用Skype for Businessします。

- ユーザーは、フロント エンド プールSkype for Business Serverする必要があります。

- 監視データベースが展開されSkype for Business Serverプールに関連付けられているSkype for Business Serverがあります。

- 通話品質ダッシュボード (CQD) を展開することをお勧めします。

## <a name="configure-rate-my-call"></a>自分の通話のレートを構成する

[通話の割合] 機能は、クライアント ポリシーで既定で有効になっています。設定は次のとおりです。

- 通話の表示割合を評価する - 10%

- 通話の評価 カスタム ユーザー フィードバックを許可する - 無効

ただし、基本機能を有効にする操作は必要ありませんが、カスタム フィードバックを必要とする場合は、個別に有効にする必要があります。 次のWindows PowerShellコマンドレットは、カスタム エンド ユーザーフィードバックを有効にし、間隔を 10% から 80% に変更する例です。

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>自分の通話データのレートにアクセスする

ユーザーからのデータは、監視データベース内の 2 つのテーブルに収集されます。

 **[QoeMetrics]。[dbo]。[CallQualityFeedbackToken]** - この表には、エンド ユーザーによるトークン ポーリングの結果が含まれます。

 **[QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef]** - このテーブルにはトークン定義が含まれます。

トークン定義は次のようにコード化されます。

|||
|:-----|:-----|
|1  <br/> |歪んだSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3  <br/> | BackgroundNoise <br/> |
|4   <br/> |MuffledSpeech  <br/> |
|5   <br/> |Echo  <br/> |
| 21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|23  <br/> | BlurryImage <br/> |
|24  <br/> | PoorColor <br/> |
|25  <br/> | DarkVideo <br/> |
|101  <br/> |Audio_SilentLocal  <br/> |
|102  <br/> |Audio_SilentRemote  <br/> |
|103  <br/> |Audio_Echo  <br/> |
|104  <br/> |Audio_BackgroundNoise  <br/> |
|105  <br/> |Audio_LowSound  <br/> |
|106  <br/> |Audio_Dropped  <br/> |
|107  <br/> |Audio_DistortedSpeech  <br/> |
|108  <br/> |Audio_Interrupted  <br/> |
|109  <br/> |Audio_Other  <br/> |
|201  <br/> |Video_NoLocalVideo  <br/> |
|202  <br/> |Video_NoRemoteVideo  <br/> |
|203  <br/> |Video_LowQuality  <br/> |
|204  <br/> |Video_FrozenVideo  <br/> |
|205  <br/> |Video_StoppedUnexpectedly  <br/> |
|206  <br/> |Video_DarkVideo  <br/> |
|207  <br/> |Video_NoAudioSync  <br/> |
|208  <br/> |Video_Other  <br/> |
|301  <br/> |Pstn_DialPad  <br/> |
|401  <br/> |SS_NoContentLocal  <br/> |
|402  <br/> |SS_NoContentRemote  <br/> |
|403  <br/> |SS_CantPresent  <br/> |
|404  <br/> |SS_LowQuality  <br/> |
|405  <br/> |SS_Freezing  <br/> |
|406  <br/> |SS_StoppedUnexpectedly  <br/> |
|407  <br/> |SS_LargeDelay  <br/> |
|408  <br/> |SS_Other  <br/> |
|501  <br/> |Reliabilty_Join  <br/> |
|502  <br/> |Reliabilty_Invite  <br/> |

 **[QoeMetrics]。[dbo]。[CallQualityFeedback]** この表には、"Star" 投票のポーリング結果と、有効な場合の顧客フィードバックが含まれている。

テーブルからのデータは **\* 、[Table.Name]** クエリからの選択を使用するか、クエリを使用してMicrosoft SQL Server Management Studio。

次のSQLクエリを使用できます。

 **Audio**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 **Video**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a>トークン定義の更新

最新のSkype for Businessクライアントは、[QoeMetrics]に存在しない可能性がある新しい問題トークン ID \> (100) を報告します。[dbo]。[CallQualityFeedbackTokenDef] テーブル。 データベース テーブルを最新のトークン定義で更新するには、次の SQL コマンドを使用して監視データベースで実行Microsoft SQL Server Management Studio。 このコマンドは[QoeMetrics]のすべてのエントリを置き換える。[dbo]。[CallQualityFeedbackTokenDef] テーブル。

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


