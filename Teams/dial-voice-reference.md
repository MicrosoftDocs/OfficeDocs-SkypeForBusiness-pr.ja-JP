---
title: 自動応答と通話キューのダイヤルと音声認識のリファレンス
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Teamsの自動応答と通話キューのダイヤルと音声認識のオプションについて説明します。
ms.openlocfilehash: 784dcbf16c5122c165dc1a949fa237769c9837d3
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124192"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自動応答と通話キューのダイヤルと音声認識のリファレンス

名前または拡張機能によるダイヤルは、発信者が組織内のTeamsユーザーにアクセスできるようにする自動応答機能です。 音声または電話のキーパッドの呼び出し元を使用すると、連絡を取る相手の完全な名前または部分名、または拡張子を言ったり入力したりできます。 自動応答は、会社のディレクトリを検索し、ユーザーを見つけて、発信者を転送します。  名前によるダイヤルまたは内線番号によるダイヤルは、 [自動応答で通話フロー設定を構成](create-a-phone-system-auto-attendant.md?tabs=call-flow)するときに設定するオプションです。

## <a name="searching-for-users"></a>ユーザーの検索

ダイヤル バイ ネームを使用してアクセスできるTeamsユーザー **は、電話番号を持っているか、通話プランが割り当てられている必要はありませんが、Skype for Business Server ユーザーに対して有効エンタープライズ VoIP必要があります**。 複数の国の組織の場合、名前でダイヤルすると、さまざまな国または地域にいるMicrosoft Teamsユーザーに発信者が検索され、転送されます。

ダイヤルバイ拡張機能を使用してアクセスできるTeamsユーザー **は、電話番号を持っているか、通話プランが割り当てられている必要はありませんが、Skype for Business Server ユーザーに対して有効エンタープライズ VoIP必要があります**。 また、ユーザーに対して適切に構成されたダイヤル プランが必要です。 複数の国内組織の場合、ダイヤル バイ 拡張機能は、さまざまな国または地域にいるMicrosoft Teamsユーザーを検索して転送します。

必要な前提条件を考慮して、自動応答を構成するときに、名前または拡張機能によるダイヤルを明示的に有効にする必要があります。

### <a name="maximum-directory-size"></a>最大ディレクトリ サイズ

呼び出し元が特定のユーザーを検索するときにサポートできる Active Directory ユーザーの数に制限はありません。 呼び出し元は、一部または完全な名前 (FirstName + LastName、および LastName + FirstName) を入力できますが、完全な内線番号が必要です。 1 人の自動応答が音声認識を使用してサポートできる名前リストの最大サイズは 80,000 ユーザーです。
  
|入力の種類|検索の形式|組織内の最大ユーザー数|
|:-----|:-----|:-----|
|DTMF (キーパッド入力) |部分  <br/> FirstName + LastName  <br/> LastName + FirstName |制限なし  |
|スピーチ (音声入力) |Firstname  <br/> Lastname  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80,000 ユーザー |

> [!NOTE]
> 音声認識で名前によるダイヤルを使用しているが、組織の Active Directory が 80,000 ユーザーを超え、 [ダイヤル スコープ](create-a-phone-system-auto-attendant.md?tabs=dial-scope) 機能を使用して名前によるダイヤルの範囲を制限していない場合、ダイヤルバイネームは電話キーパッドを使用して発信者に対して引き続き機能し、音声入力は他のすべてのシナリオで使用できます。 ダイヤル範囲機能を使用して、名前でダイヤル機能の範囲を変更することによってアクセスできる名前を、特定の自動応答に絞り込むことができます。

### <a name="search-considerations"></a>検索に関する考慮事項

ダイヤル バイ ネームは、最初に組織全体のディレクトリを検索してから、構成されているダイヤル スコープのインクルードまたは除外リストを適用します。 ディレクトリ全体に対する最初の検索で 100 人を超えるユーザーが返された場合、ダイヤル スコープリストは適用されず、検索は失敗し、呼び出し元は名前が多すぎることが通知されます。

## <a name="dial-by-name---keypad-dtmf-entry"></a>名前でダイヤル - キーパッド (DTMF) 入力

呼び出し元のユーザーは、ダイヤルバイネームを使用して、アクセスしようとしているユーザーの完全な名前または部分的な名前を指定してユーザーに連絡できます。 名前を入力するときに使用できるさまざまな形式があります。

組織のディレクトリを検索するときに、ユーザーは '0' (ゼロ) キーを使用して、名と姓と名の間のスペースを示すことができます。 名前を入力すると、# キーを使用してキーパッドエントリを終了するように求められます。 たとえば、「到達しようとしているユーザーの名前を入力したら、#キーを押します」とします。 複数の名前が見つかった場合は、呼び出し元のユーザーに、選択する名前の一覧が表示されます。

> [!NOTE]
> ダイヤル スコープの含めるリストまたは除外リストが適用された後に 5 つを超える名前が残っている場合、検索は失敗し、呼び出し元に見つかった名前が多すぎることが通知されます。
  
電話機のキーパッドで次の検索形式を使用して組織内の名前を検索できます。
  
|名前の形式|検索の種類|例|検索結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |完全  |Amos0Marble# |Amos Marble |
|LastName + FirstName |完全 |Marble0Amos#  |Amos Marble |
|Firstname  |完全   |Amos#   |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |
|Lastname |完全 |Marble#  |Amos Marble の場合は 1 を押す  <br/> Mary Marble の場合は 2 を押す |
|FirstName または LastName |部分 |Mar# |Mary Marble の場合は 1 を押す  <br/> Mary Jones の場合は 2 を押す  <br/> Amos Marcus の場合は 3 を押す |
|FirsName + LastName |部分 |Amos0Mar# |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |
|LastName + FirstName |部分 |Mar0Am# |Amos Marble の場合は 1 を押す  <br/> Amos Marcus の場合は 2 を押す |

電話機のキーパッドを使用してユーザーを検索するときに使われる特殊文字がいくつかあります。 たとえば、ユーザーはポンド キー (#)を使用するように求められますが、名前の間のスペースにはゼロ (0) キーが使用されます。 アスタリスク キー (*) を押すと、特定のユーザーに一致する名前の一覧を繰り返します。
  
|電話機のキーパッドの特殊文字|意味|
|:-----|:-----|
|#   |名前入力時の終了文字です。 |
|0   |名前の間のスペースです。 |
|*    |一致する名前のリストを繰り返します。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>名前でダイヤル - 音声による名前認識

ユーザーは、自分の音声 (音声認識) を使用して組織内の他のユーザーを検索できます。 また、検索しようとしているユーザーの完全な名前または部分名を言って、Active Directory 内のすべてのユーザーにアクセスすることもできます。 音声入力を使用すると、FirstName、LastName、FirstName + LastName、LastName + FirstName など、さまざまな形式の名前を認識できます。
  
自動応答で音声認識を有効にできますが、電話キーパッド エントリ (DTMF) は無効にされていません。 電話キーパッドエントリは、自動応答で音声認識が有効になっている場合でも、いつでも使用できます。
  
電話のキーパッドエントリと同様に、複数の名前が見つかった場合、呼び出し元のユーザーは選択する名前の一覧を読み上げられます。

> [!NOTE]
> ダイヤル スコープの含めるリストまたは除外リストが適用された後に 5 つを超える名前が残っている場合、検索は失敗し、呼び出し元に見つかった名前が多すぎることが通知されます。
  
呼び出し元は、次の形式で名前を言うことができます。
  
|音声を含む名前|検索の種類|例|検索結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |完全 |Amos Marble |Amos Marble |
|LastName + FirstName |完全  |Marble Amos |Amos Marble |
|Firstname |完全 |Amos |Amos Marble の場合は 1 を押すか 1 と言う  <br/> Amos Jones の場合は 2 を押すか 2 と言う |
|Lastname |完全 |Marble |Amos Marble の場合は 1 を押すか 1 と言う  <br/> Ben Marble の場合は 2 を押すか 2 と言う |
|FirstName または LastName |部分 |03 月 |Mary Marble で 1 を押すか、または 1 と言う  <br/> Mary Jones で 2 キーを押すか、または 2 と入力します  <br/> Amos Skuus で 3 キーを押すか、または 3 と入力します |
|FirsName + LastName |部分 |Amos Mar |Amos Marble の場合は 1 を押すか 1 と言う  <br/> Amos Skuus で 2 キーを押すか、または 2 と入力します |

> [!NOTE]
> Active Directory レプリケーションラグのため、新しいユーザーが音声認識を使用して Dial by Name のディレクトリに名前を表示するには、最大で 36 時間かかる場合があります。

### <a name="dial-by-extension"></a>内線番号によるダイヤル

**ダイヤルバイ拡張機能** を使用できるようにするユーザーは、Active Directory で定義されている次の電話属性の一部として拡張機能を指定する必要があります (Azure AD Connectを使用して同期)、またはAzure Active Directory。 (詳細については、「 [ユーザーを個別または一括で追加](/microsoft-365/admin/add-users/add-users) する」を参照してください)。

- OfficePhone/PhoneNumber (AD と Azure AD)
- HomePhone (AD)
- Mobile/MobilePhone (AD と Azure AD)
- OtherTelephone (AD)

ユーザーの電話番号フィールドに内線番号を入力するために必要な形式は、次のいずれかの形式になります。

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- 例 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- 例 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- 例 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

拡張機能は、[Microsoft 365 管理センター](https://admin.microsoft.com/)または[Azure Active Directory管理センター](https://aad.portal.azure.com)で設定できます。 自動応答と呼び出しキューに変更が使用可能になるまでには、最大で 12 時間かかる場合があります。

## <a name="language-support"></a>言語のサポート

テキスト読み上げと音声認識の言語サポートは、 [サポートされているこれらの言語](create-a-phone-system-auto-attendant-languages.md)で利用できます。

音声認識には、次の音声コマンドを使用できます。
  
|音声コマンド| に対応します。 |
|:-----|:-----|
|はい | [はい] で 1 キーを押します。 |
|いいえ | [いいえ] に 2 キーを押します。 |
|繰り返し |オプションの一覧を繰り返します。 キーパッドの * キーを押して、オプションの一覧を繰り返します。 |
|オペレーター | "Operator" に 0 キーを押す |
|メイン メニュー  |通話者を自動応答のメイン メニューに移動させます。 |
|ゼロ | 0 キーを押します (既定では"演算子" と同じです)。|
|イチ | 1 キーを押します。 |
|ニ | 2 キーを押します。 |
|サン| 3 キーを押します。|
|ヨン | 4 キーを押します。 |
|ゴ | 5 キーを押します。 |
|ロク  | 6 キーを押します。 |
|ナナ | 7 キーを押します。|
|ハチ |8 キーを押します。|
|キュウ  |9 キーを押します。|

## <a name="related-topics"></a>関連項目

[Skype for Business および Microsoft Teams のサービス電話番号の取得](./getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
