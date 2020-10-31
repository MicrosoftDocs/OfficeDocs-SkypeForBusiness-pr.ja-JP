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
description: Teams の自動応答と通話キューのダイヤルと音声認識のオプションについて説明します。
ms.openlocfilehash: 3e3e750ff28779fb8fe8765a088c5a65d2a9b1f0
ms.sourcegitcommit: 273f231098799975dc4cf609a68c9944b8072ce1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "48818807"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自動応答と通話キューのダイヤルと音声認識のリファレンス

名前によるダイヤルは自動応答の機能であり、ディレクトリ検索とも呼ばれます。 自動応答を呼び出しているユーザーが音声 (音声認識) または電話のキーパッド (DTMF) 応答を使用できるようにして、会社のディレクトリを検索し、その人を検索してから、通話を転送することができます。 [自動応答でコールフローの設定を構成](create-a-phone-system-auto-attendant.md#call-flow)する場合は、名前でダイヤルを設定します。

## <a name="searching-for-users"></a>ユーザーを検索する

[名前を付けてダイヤルする] を使用して、電話番号を割り当てる必要があります。また、通話プランを割り当てられているユーザーは、電話のシステムライセンスを持っている必要があります。 **また、オンラインユーザーの場合、または Skype For Business Server ユーザーのエンタープライズボイスが有効になっている場合は、電話システムライセンスが** 必要 名前でダイヤルすると、複数の国や地域でホストされている Microsoft Teams ユーザーへの通話を検索して転送することもできます。 前提条件が満たされている場合は、自動応答で名前でダイヤルできるようにする必要があります。

内線番号は、ディレクトリ検索の一部でもある自動応答の機能です。 自動応答を呼び出したユーザーが音声 (音声認識) または電話のキーパッド (DTMF) 応答を使用できるようにして、通話を発信しているユーザーの内線番号を入力してから、通話を転送することができます。 ダイヤルして内線番号を使用しているユーザーに  **は、電話番号を設定したり、通話プランを割り当てたりする必要はありませんが、オンラインユーザーの場合は電話システムライセンス、Skype For Business Server ユーザーの場合はエンタープライズボイスを有効** にする必要があります。 また、ユーザーに対して適切に設定されたダイヤルプランが必要です。 内線番号を指定すると、複数の国や地域でホストされている Microsoft Teams ユーザーへの通話を検索して転送することができます。 前提条件が満たされている場合は、自動応答で内線番号を明示的に有効にします。

### <a name="maximum-directory-size"></a>最大ディレクトリ サイズ

ユーザーが特定のユーザーを検索するときに、[名前によってダイヤルする] および [内線番号] でダイヤルできる Active Directory ユーザーの数に制限はありません。 発信者は、部分名または完全な名前 (姓 + 姓、および LastName + 名) を入力できますが、完全な内線番号が必要です。 音声認識を使って1つの自動応答でサポートできる名前リストの最大サイズは、8万ユーザーです。
  
|入力の種類|検索の形式|組織内の最大ユーザー数|
|:-----|:-----|:-----|
|DTMF (キーパッド入力) |部分  <br/> FirstName + LastName  <br/> LastName + FirstName |制限なし  |
|スピーチ (音声入力) |担当  <br/> 姓  <br/> FirstName + LastName  <br/> LastName + FirstName  | 8万ユーザー |

> [!NOTE]
> 音声認識で名前でダイヤルを使用していても、組織の Active Directory が8万ユーザーよりも大きく、ダイヤルの範囲機能を使用して名前によるダイヤルの範囲を制限していない場合は、電話のキーパッドを使って、発信者に名前でダイヤルできます。音声入力は、他のすべてのシナリオでも利用できます ダイヤル範囲機能を使用して、名前でダイヤル機能の範囲を変更することによってアクセスできる名前を、特定の自動応答に絞り込むことができます。
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>名前でダイヤル - キーパッド (DTMF) 入力
通話相手は、名前でダイヤルすることで、ユーザーに連絡する相手の完全名または一部名のいずれかを指定することができます。 名前を入力するときに使用できるさまざまな形式があります。

組織のディレクトリを検索する場合、ユーザーは "0" (ゼロ) キーを使用して名と姓または名の間にスペースを指定できます。 ユーザーが名前を入力すると、キーパッドのエントリを # キーで終了するかどうかをたずねるメッセージが表示されます。 たとえば、"通話相手の名前を入力した後、#." と入力します。 見つかった名前が複数ある場合は、そのユーザーに対して選択する名前の一覧が表示されます。
  
電話機のキーパッドで次の検索形式を使用して組織内の名前を検索できます。
  
|名前の形式|検索の種類|例|検索結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |完全  |Amos0Marble# |Amos Marble |
|LastName + FirstName |完全 |Marble0Amos#  |Amos Marble |
|担当  |完全   |Amos#   |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |
|姓 |完全 |Marble#  |Amos Marble の場合は 1 を押す  <br/> Mary Marble の場合は 2 を押す |
|FirstName または LastName |部分 |Mar# |Mary Marble の場合は 1 を押す  <br/> Mary Jones の場合は 2 を押す  <br/> Amos Marcus の場合は 3 を押す |
|FirsName + LastName |部分 |Amos0Mar# |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |
|LastName + FirstName |部分 |Mar0Am# |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |

電話機のキーパッドを使用してユーザーを検索するときに使われる特殊文字がいくつかあります。 たとえば、シャープキー (#) を使用するように求められますが、名前の間のゼロ (0) キーはスペースに使用されます。 アスタリスク キー (*) を押すと、特定のユーザーに一致する名前の一覧を繰り返します。
  
|電話機のキーパッドの特殊文字|意味|
|:-----|:-----|
|#   |名前入力時の終了文字です。 |
|0   |名前の間のスペースです。 |
|*    |一致する名前のリストを繰り返します。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>名前でダイヤル - 音声による名前認識

ユーザーは、音声 (音声認識) を使って、組織内の他のユーザーを検索できます。 また、検索しようとしているユーザーの名前を言うことで、Active Directory 内のすべてのユーザーに連絡することもできます。 音声入力を使うと、姓、名、姓 + 名、LastName + 名など、さまざまな形式の名前を認識できます。
  
自動応答で音声認識を有効にすることはできますが、電話のキーパッド入力 (DTMF) は無効になりません。 自動応答で音声認識が有効になっている場合でも、電話のキーパッドエントリをいつでも使うことができます。
  
電話機のキーパッド入力と同様に、複数の名前が見つかると、通話を発信した人が名前の一覧を聞くことができます。
  
発信者は、次の形式で名前を読み上げることができます。
  
|音声での名前|検索の種類|例|検索結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |完全 |Amos Marble |Amos Marble |
|LastName + FirstName |完全  |Marble Amos |Amos Marble |
|担当 |完全 |Amos |Amos Marble の場合は 1 を押すか 1 と言う  <br/> Amos Jones の場合は 2 を押すか 2 と言う |
|姓 |完全 |Marble |Amos Marble の場合は 1 を押すか 1 と言う  <br/> Ben Marble の場合は 2 を押すか 2 と言う |

> [!NOTE]
> Active Directory のレプリケーションの遅延のため、新しいユーザーが名前をダイヤルするディレクトリに名前を付けて、音声認識によって名前が表示されるまでに最大36時間かかることがあります。
  
## <a name="language-support"></a>言語のサポート

次の言語は、送信プロンプトで使用される音声合成で使用できます。
  
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

自動応答の音声認識入力は、次の言語で利用できます。
  
|-|-|
|:-----|:-----|
|中国語 (ZH)  |フランス語 (FR)  |
|英語 (AU)  |ドイツ語 (DE)  |
|英語 (CA)  |イタリア語 (IT)  |
|英語 (IN)  |日本語 (JP)  |
|英語 (U.K.)  |ポルトガル語 (BR)  |
|英語 (米国)  |スペイン語 (ES)  |
|フランス語 (CA)   |スペイン語 (MX)  |

音声認識用にサポートされている14言語では、次の音声コマンドを利用できます。
  
|音声コマンド| 対応する |
|:-----|:-----|
|はい | [はい] の場合は1を押します。 |
|いいえ | いいえには2を押します。 |
|繰り返し |オプションの一覧を繰り返します。 キーパッドの * キーを押して、オプションの一覧を繰り返します。 |
|オペレーター | "Operator" の場合は0を押します。 |
|メイン メニュー  |通話者を自動応答のメイン メニューに移動させます。 |
|ゼロ | 0 (既定では "Operator" と同じ) を押します。|
|イチ | 1を押します。 |
|ニ | 2キーを押します。 |
|サン| 3キーを押します。|
|ヨン | 4キーを押します。 |
|ゴ | 5キーを押します。 |
|ロク  | 6キーを押します。 |
|ナナ | 7キーを押します。|
|ハチ |8キーを押します。|
|キュウ  |9キーを押します。|

## <a name="related-topics"></a>関連項目

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](/microsoftteams/getting-service-phone-numbers)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[小規模ビジネスの例: 自動応答をセットアップする](/microsoftteams/tutorial-org-aa)
