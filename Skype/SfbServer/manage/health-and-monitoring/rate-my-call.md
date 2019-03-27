---
title: Business Server に Skype で電話を評価する.
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '概要: は、ビジネス サーバー用のレート自分を呼び出す機能は、Skype について説明します。'
ms.openlocfilehash: 61aaff26c5786cd8574b7277ed600da75c3679ce
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886304"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Business Server に Skype で電話を評価する.

**の概要:** ビジネス サーバーのマイ レートを呼び出す機能は、Skype を紹介します。

レート [呼び出すビジネス 2015年 2016 上およびクライアント企業のエンド ・ ユーザーからのフィードバックを取得する方法を提供する Windows 用 Skype の新機能をしました。

レート [呼び出し] ウィンドウでは、「星」の評価システムと音声通話とビデオ通話用の定義済みのトークンを提供します。 さらに、管理者には、フィードバックを提供するユーザー設定フィールドが有効にすることができます。

レート [呼び出しの収集したデータが既存の監視のレポートに現在含まれていないが、監視、別のレポートがあります。 SQL クエリを実行することによってアクセスできる SQL テーブル内のデータが収集されます。

## <a name="rate-my-call-prerequisites"></a>通話の評価の前提条件

ビジネス サーバーの展開について、Skype のユーザーは、レートの [呼び出しの機能にアクセスできる、前に次のコンポーネントのセットを展開し、構成する必要があります。

-  ビジネスのサーバーにインストールされている (9160 またはそれ以降のバージョン) には、Skype が必要です。

- もらって、Skype を使用して、ビジネスの ui をインストールし、ビジネスの Skype の最新バージョンへの更新は、ユーザーがいます。

- ビジネス サーバーのフロント エンド プールの Skype では、ユーザーが所属する必要があります。

- ビジネス サーバー監視のデータベースを展開し、Skype をビジネス サーバー プールに関連付けられているため、Skype が必要です。

- 通話品質ダッシュボード (CQD) を展開することをお勧めします

## <a name="configure-rate-my-call"></a>通話の評価の構成

レート自分を呼び出す機能は既定では、次の設定でクライアントのポリシーを有効になっています。

- [呼び出し表示の割合の 10% を評価します。

- 呼び出しできるようにするカスタム ユーザー フィードバック - 無効になっている評価します。

ただし、基本機能を有効にする必要がありませんが、カスタムのフィードバックをする場合は個別に有効にする必要があります。。 次の Windows PowerShell コマンドレットでは、カスタムのエンド ・ ユーザーからのフィードバックを有効にし、10% から 80% に変更する例を示します。

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>通話の評価データへのアクセス

監視データベース内の 2 つのテーブルでは、ユーザーからのデータが収集されます。

 **[QoeMetrics] です。[dbo].[CallQualityFeedbackToken]**-次の表には、エンド ・ ユーザーによるトークンのポーリングの結果が含まれています。

 **[QoeMetrics] です。[dbo].[CallQualityFeedbackTokenDef]**-次の表には、トークンの定義が含まれています。

トークンの定義は、次のように記述します。

|||
|:-----|:-----|
|1  <br/> |DistortedSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3  <br/> | BackgroundNoise <br/> |
|4  <br/> |MuffledSpeech  <br/> |
|5  <br/> |Echo  <br/> |
|21  <br/> | FrozenVideo <br/> |
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

 **[QoeMetrics] です。[dbo].[CallQualityFeedback]** このテーブルには、有効になっている場合の「星」の投票および顧客のフィードバックからのポーリングの結果が含まれています。

テーブルからデータを使用して呼び出すことができます、**を選択\*[Table.Name] から**クエリまたは Microsoft SQL Server Management Studio のを使用しています。

次の SQL クエリを使用できます。

 **音声**

```
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

 **ビデオ**

```
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

## <a name="updating-token-definitions"></a>トークンの定義を更新します。

ビジネス クライアント用の最新の Skype は、新しい問題トークン Id を報告 (\> 100)、[QoeMetrics] 内に存在できません。[dbo].[CallQualityFeedbackTokenDef] テーブルです。 最新のトークン定義とデータベース テーブルを更新するのには、Microsoft SQL Server Management Studio のを使用して監視データベースに SQL の下コマンドを実行することができます。 このコマンドは、[QoeMetrics] 内のすべてのエントリに置き換えられます。[dbo].[CallQualityFeedbackTokenDef] テーブルです。

```
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


