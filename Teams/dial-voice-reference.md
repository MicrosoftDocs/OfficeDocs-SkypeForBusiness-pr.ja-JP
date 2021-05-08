---
title: 自動応答と通話キューのダイヤルと音声認識のリファレンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 自動応答と通話キューのダイヤルと音声認識のオプションについては、Teams。
ms.openlocfilehash: f62a04735d386637489d52956e6a064a2eba1e4e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098443"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自動応答と通話キューのダイヤルと音声認識のリファレンス

[名前でダイヤル] は、ディレクトリ検索とも呼ばれる自動応答の機能です。 これにより、自動応答を呼び出すユーザーは、音声 (音声認識) または電話キーパッド (DTMF) 応答を使用して、会社のディレクトリを検索し、その人を見つけ、通話を転送するために完全または部分的な名前を入力できます。 自動応答 でコール フロー設定を構成するときに、名前で [ダイヤルを設定します](create-a-phone-system-auto-attendant.md#call-flow)。

## <a name="searching-for-users"></a>ユーザーの検索

[エンタープライズ VoIP 名前でダイヤル] を使用してアクセスしたユーザーは、電話番号や通話プランが割り当てられている必要はありません。ただし、Skype for Business Server ユーザーに対して有効にする必要 **があります**。 名前でダイヤルすると、複数の国や地域でホストされているMicrosoft Teamsユーザーに通話を検索して転送できます。 前提条件を満たす場合は、自動応答で [名前でダイヤル] を明示的に有効にしてください。

内線番号によるダイヤルは、ディレクトリ検索の一部である自動応答の機能です。 これにより、自動応答を呼び出すユーザーは、音声 (音声認識) または電話のキーパッド (DTMF) 応答を使用して、到達しようとしているユーザーの内線番号を入力し、通話を転送することができます。 [内線 **エンタープライズ VoIP** 番号でダイヤル] を使用してアクセスしたユーザーは、電話番号を持っている必要も、通話プランも割り当てられている必要はありません。ただし、Skype for Business Server ユーザーに対して有効にする必要があります。 また、ユーザー用に適切に構成されたダイヤル プランが必要です。 内線番号でダイヤルすると、複数の国や地域でホストされている Microsoft Teams ユーザーに通話を検索して転送することもできます。 必要な前提条件を満たす場合は、自動応答で [内線番号によるダイヤル] を明示的に有効にしてください。

### <a name="maximum-directory-size"></a>最大ディレクトリ サイズ

発信者が特定のユーザーを検索するときにサポートできる Active Directory ユーザーの数に制限はありません。 呼び出し元は、部分的または完全な名前 (FirstName + LastName、LastName + FirstName) を入力できますが、完全な内線番号が必要です。 1 つの自動応答が音声認識を使用してサポートできる名前リストの最大サイズは、80,000 人のユーザーです。
  
|入力の種類|検索の形式|組織内の最大ユーザー数|
|:-----|:-----|:-----|
|DTMF (キーパッド入力) |部分  <br/> FirstName + LastName  <br/> LastName + FirstName |制限なし  |
|スピーチ (音声入力) |FirstName  <br/> LastName  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80,000 ユーザー |

> [!NOTE]
> 音声認識で名前によるダイヤルを使用しているが、組織の Active Directory が 80,000 人を超え、ダイヤル スコープ機能を使用して名前でダイヤルの範囲を制限していない場合、ダイヤル バイ ネームは電話のキーパッドを使用して発信者に対して引き続き機能し、音声入力は他のすべてのシナリオで使用できます。 ダイヤル範囲機能を使用して、名前でダイヤル機能の範囲を変更することによってアクセスできる名前を、特定の自動応答に絞り込むことができます。
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>名前でダイヤル - キーパッド (DTMF) 入力
コールインするユーザーは、ダイヤル バイ ネームを使用して、到達しようとしているユーザーの完全な名前または部分的な名前を指定することで、ユーザーに到達できます。 名前を入力するときに使用できるさまざまな形式があります。

組織のディレクトリを検索するときに、ユーザーは '0' (ゼロ) キーを使用して、名と名または名と名の間のスペースを示します。 名前を入力すると、キーパッドのエントリを # キーで終了する必要があります。 たとえば、"到達しようとしているユーザーの名前を入力した後、#キーを押します"。 複数の名前が見つかった場合、呼び出し元のユーザーには、選択する名前の一覧が表示されます。
  
電話機のキーパッドで次の検索形式を使用して組織内の名前を検索できます。
  
|名前の形式|検索の種類|例|検索結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |完全  |Amos0Marble# |Amos Marble |
|LastName + FirstName |完全 |Marble0Amos#  |Amos Marble |
|FirstName  |完全   |Amos#   |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |
|LastName |完全 |Marble#  |Amos Marble の場合は 1 を押す  <br/> Mary Marble の場合は 2 を押す |
|FirstName または LastName |部分 |Mar# |Mary Marble の場合は 1 を押す  <br/> Mary Jones の場合は 2 を押す  <br/> Amos Marcus の場合は 3 を押す |
|FirsName + LastName |部分 |Amos0Mar# |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |
|LastName + FirstName |部分 |Mar0Am# |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |

電話機のキーパッドを使用してユーザーを検索するときに使われる特殊文字がいくつかあります。 たとえば、名前の間のスペースにはゼロ (0) キーが使用され、シャープキー (#)を使用する必要があります。 アスタリスク キー (*) を押すと、特定のユーザーに一致する名前の一覧を繰り返します。
  
|電話機のキーパッドの特殊文字|意味|
|:-----|:-----|
|#   |名前入力時の終了文字です。 |
|0   |名前の間のスペースです。 |
|*    |一致する名前のリストを繰り返します。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>名前でダイヤル - 音声による名前認識

ユーザーは自分の声 (音声認識) で組織内の他のユーザーを検索できます。 また、検索しようとしているユーザーの完全な名前または一部の名前を言って、Active Directory 内のすべてのユーザーにアクセスできます。 音声入力を使用すると、FirstName、LastName、FirstName + LastName、LastName + FirstName など、さまざまな形式で名前を認識できます。
  
自動応答で音声認識を有効にできますが、電話のキーパッド入力 (DTMF) は無効にされません。 電話キーパッドの入力は、自動応答で音声認識が有効になっている場合でも、いつでも使用できます。
  
電話のキーパッド入力と同様に、複数の名前が見つかった場合、呼び出し元のユーザーが選択する名前のリストが聞こえます。
  
呼び出し元は、次の形式で名前を言います。
  
|音声付き名前|検索の種類|例|検索結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |完全 |Amos Marble |Amos Marble |
|LastName + FirstName |完全  |Marble Amos |Amos Marble |
|FirstName |完全 |Amos |Amos Marble の場合は 1 を押すか 1 と言う  <br/> Amos Jones の場合は 2 を押すか 2 と言う |
|LastName |完全 |Marble |Amos Marble の場合は 1 を押すか 1 と言う  <br/> Ben Marble の場合は 2 を押すか 2 と言う |
|FirstName または LastName |部分 |3 月 |Mary Marble の場合は 1 を押す、または 1 と言う  <br/> Mary Jones の場合は 2 キーを押す、または 2 と言う  <br/> Amos Marcus で 3 キーを押す、または言う |
|FirsName + LastName |部分 |Amos Mar |Amos Marble の場合は 1 を押すか 1 と言う  <br/> Amos Marcus で 2 キーを押す、または言う |


> [!NOTE]
> Active Directory レプリケーションの遅延により、新しいユーザーの名前が音声認識を使用して名前でダイヤルのディレクトリに表示されるには、最大で 36 時間かかる場合があります。
  
## <a name="language-support"></a>言語のサポート

送信プロンプトで使用されるテキスト読み上げでは、次の言語を使用できます。
  
|-|-|-|
|:-----|:-----|:-----|
|アラビア語 (EG)  |英語 (U.K.)  |韓国語 (KO)  |
|中国語 (HK)  |英語 (U.K.) |ノルウェー語 (NO)  |
|中国語 (TW) |英語 (米国) |ポーランド語 (PL)  |
|中国語 (ZH) |フィンランド語 (FI) |ポルトガル語 (BR) |
|デンマーク語 (DA)  |フランス語 (CA)  |ポルトガル語 (PT) |
|オランダ語 (NL)   |フランス語 (FR)  |ロシア語 (RU) |
|英語 (AU)  |ドイツ語 (DE) |スペイン語 (ES)  |
|英語 (CA)  |イタリア語 (IT) |スペイン語 (MX)|
|英語 (IN)  |日本語 (JP) |スウェーデン語 (SV)|

自動応答の音声認識入力は、次の言語で使用できます。
  
|-|-|
|:-----|:-----|
|中国語 (ZH)  |フランス語 (FR)  |
|英語 (AU)  |ドイツ語 (DE)  |
|英語 (CA)  |イタリア語 (IT)  |
|英語 (IN)  |日本語 (JP)  |
|英語 (U.K.)  |ポルトガル語 (BR)  |
|英語 (米国)  |スペイン語 (ES)  |
|フランス語 (CA)   |スペイン語 (MX)  |

音声認識でサポートされている 14 の言語では、次の音声コマンドを使用できます。
  
|音声コマンド| 対応 |
|:-----|:-----|
|はい | [はい] の場合は 1 キーを押します。 |
|いいえ | [いいえ] の場合は 2 キーを押します。 |
|繰り返し |オプションの一覧を繰り返します。 キーパッドの * キーを押して、オプションの一覧を繰り返します。 |
|オペレーター | "Operator" の場合は 0 キーを押します。 |
|メイン メニュー  |通話者を自動応答のメイン メニューに移動させます。 |
|ゼロ | 0 キーを押します (既定では 、"演算子" と同じです)。|
|イチ | 1 キーを押します。 |
|ニ | 2 キーを押します。 |
|サン| 3 キーを押します。|
|ヨン | 4 キーを押します。 |
|ゴ | 5 キーを押します。 |
|ロク  | 6 キーを押します。 |
|ナナ | 7 キーを押します。|
|ハチ |8 キーを押します。|
|キュウ  |9 キーを押します。|

## <a name="related-topics"></a>関連トピック

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](./getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)