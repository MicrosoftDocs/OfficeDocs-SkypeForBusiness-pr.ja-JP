---
title: PSTN の使用状況レポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: '[新しい Skype for Business 管理センターのレポート] 領域には、組織内の電話会議アクティビティと電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、Skype for Business での PSTN 使用状況の詳細レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 通話のコストなど、電話会議の PSTN 利用状況の詳細を表示して、組織内での使用状況を特定するために、使用状況を理解し、請求の詳細を呼び出すことができます。'
ms.openlocfilehash: 09d372f6526d14a65e878271a1b277fc19d7d3e4
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201171"
---
# <a name="pstn-usage-report"></a>PSTN の使用状況レポート

[新しい Skype for Business 管理センターの**レポート**] 領域には、組織内の電話会議アクティビティと電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、 **Skype for Business での PSTN 使用状況の詳細**レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 通話のコストなど、電話会議の PSTN 利用状況の詳細を表示して、組織内での使用状況を特定するために、使用状況を理解し、請求の詳細を呼び出すことができます。
  
利用可能なその他のレポートについては、 [「レポートの概要」](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
このレポートとその他の Skype for Business レポートを使用すると、組織全体での利用状況などのアクティビティについて詳しく知ることができます。 これらの情報は、組織のビジネスに関する調査、計画、その他の意思決定を行ったり、[通信クレジット](/microsoftteams/what-are-communications-credits)を設定したりする際に非常に役立ちます。
  
> [!NOTE]
> Microsoft 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Skype for Business の PSTN 使用状況詳細レポートを取得する方法

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

- 管理センターに移動して >**管理**センター  >  **Skype for business 管理センター**  >  **レポート**  >  **PSTN 使用量の詳細**をレポートします。
    
    > [!NOTE]
    > 使用している Microsoft 365 または Office 365 のサブスクリプションによっては、ここに表示される製品やレポートがすべて表示されない場合があります。
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Skype for Business PSTN 使用状況レポートを解析する

表示されている各列を見ると、ユーザーの Skype for Business PSTN 使用状況を確認できます。
  
レポートは、このように表示されます。
  
[![Skype For BUSINESS PSTN 使用状況レポート ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![ナンバー 1](../images/sfbcallout1.png)<br/>この表は、ユーザーごとの、すべての PSTN 使用状況の詳細を示しています。また、Skype for Business が割り当てられているすべてのユーザーと、ユーザーの PSTN 使用状況を示しています。表では、列を追加したり、削除したりすることができます。
*    **通話 ID** は通話の識別番号です。 これは、Microsoft サービスサポートへの通話時に使用される通話の識別子です。
*    [ **ユーザー ID**] は、ユーザーのサインイン名です。
*    **電話番号**は着信通話を受けた Skype for Business の電話番号、または発信通話でダイヤルされた番号です。
*    [**ユーザーの所在地**] は、ユーザーが所在する国/地域です。
*    **発信者 ID** は着信通話の発信者電話番号 (発信者 ID) であるか、通話の発信元の番号であるか、発信通話に対して通話の発信元となった Skype for Business 番号です。
*    [**通話の種類**] は、通話が PSTN の発信または着信であるか、ユーザーまたは電話会議による通話などの通話の種類であるかを示します。 表示される可能性のある通話の種類は次のとおりです。 

     **通話プランの通話の種類** 
     *    **user_in** (着信 PSTN 通話を受信したユーザー) 
     *    **user_out** (発信 PSTN 通話をかけたユーザー) 
     *    **user_out_conf** (2 つ以上の PSTN 参加者を 3 方向の電話会議などに追加したユーザー) 
     *    **user_out_transfer** (PSTN 番号に通話を転送したユーザー) 
     *    **user_out_forwarding** (PSTN 番号に通話を転送したユーザー)

     **電話会議の通話の種類**
     *    **conf_in** (電話会議ブリッジへの着信通話) この種類の通話のレコードの場合、[**ユーザー ID** ] 列に指定されたユーザーは、会議の開催者に対応しています。
     *    **conf_out** (通常は電話会議に PSTN 番号を追加するための電話会議ブリッジからの発信通話) この種類の通話のレコードの場合、[**ユーザー ID** ] 列に指定されたユーザーは、会議の開催者に対応しています。

     **統合コミュニケーション アプリケーション (UCAP)** 
     *    **ucap_in** (自動応答や通話キューなどの UC アプリケーションへの着信 PSTN 通話) 
     *    **ucap_out** (自動応答や通話キューなどの UC アプリケーションからの送信 PSTN 通話)
         > [!NOTE]
         > 自動応答や通話キューなどの UC アプリケーションからユーザーに転送された通話は、ピアツーピア (P2P) の音声通話であるため、PSTN 使用状況レポートには表示されません。 Skype for Business 管理センターの P2P 通話には、"ツール > Skype for Business Call Analytics" のようにアクセスして、ユーザー名または SIP アドレスで検索し、日付/時刻/発信元の CLID (呼び出し行 ID) で検索することができます。 

     [ **国内/国際**] は、ユーザーの場所に基づいて通話が国内 (国/地域内) または国際 (国/地域外) のどちらと見なされるかを示します。 
*    [**宛先ダイヤル**] は、フランス、ドイツ、または米国 (米国) などのダイヤル先の国/地域の名前です。 
*    [**番号の種類**] は、ユーザーの電話番号、サービス、またはフリーダイヤル番号からの電話番号の種類です。  
*    [ **開始時刻 (UTC)**] は、通話が開始または実行された時刻です。 
*    [ **通話時間**] は、通話が接続されていた時間です。  
*    **ConfID** は電話会議の電話会議 ID です。 
*    [ **料金**] は、アカウントに課金される金額または通話の料金です。 
*    [ **通貨**] は、通話の料金を計算するために使用される通貨の種類です。 
*    [ **機能** ] は通話のために使用されるライセンスです。表示されるライセンスの種類は次のとおりです。 
     *    **Mcopstnpp** -通信クレジット <br/> **MCOPSTN1** -国内通話プラン (3000 分間/1200 分の EU プラン) 
     *    **MCOPSTN2** -国際通話プラン 
     *    **MCOPSTN5** -国内通話プラン (120 分の通話プラン) 
     *    **MCOPSTN6** -国内通話プラン (240 分間通話プラン) 注: 利用制限
     *    **MCOMEETADD** -電話会議
     *    **MCOMEETACPEA** -1 分あたりの通話料金電話会議
     
> [!NOTE]
> 通話または会議サブスクリプションに含まれていない1分あたりの通話のみを含めるレポートを実行する場合は、機能 "MCOPSTNPP" を使用してレポートをフィルター処理します。 これにより、1分あたりの通話料金の明細が提供されます。  1分あたりの通話料金の場合は、"MCOPSTNPP" の代わりに "MCOMEETACPEA" でフィルター処理します。  

> [!NOTE]
> 一部のフィールドに "データなし" と表示されることもあります。 "データなし" は、このフィールドが通話の種類または機能に適用されないことを意味します。 

> [!NOTE]
> Telstra または Softbank 通話プランをお持ちの場合は、PSTN 使用状況レポートに通話の詳細レコードは表示されません。 レポートのニーズについては、Telstra または Softbank にお問い合わせください。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。
 ***

## <a name="exporting-pstn-usage-report"></a>PSTN 使用状況レポートのエクスポート

[ **Excel にエクスポート**] ボタンをクリックまたはタップすると、PSTN 使用状況レポートをダウンロードできます。 国固有の規制により、12ヶ月のデータの保持を禁止する場合を除き、現在の日付から1年後にデータをエクスポートすることができます。

これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。

データの量によっては、エクスポートプロセスが完了するまで数秒かかることがあります。 サーバーでエクスポートが完了すると、"**Calls. [] という名前の zip ファイルが送信されます。 `identifier`zip**"。識別子がエクスポートの一意の ID となります。これは、トラブルシューティングに使用できます。

通話プランと直接ルーティングの両方を使用している場合、エクスポートされたファイルには両方の製品のデータが含まれている可能性があります。 PSTN 使用状況レポートファイルのファイル名が "**pstn. [] になってい `UTC date` ます。csv**"。 PSTN とダイレクトルーティングファイルに加えて、アーカイブには、選択したエクスポート時間の範囲と機能 (存在する場合) を含む "**parameters.js**" というファイルが含まれています。

エクスポートされたファイルは、 [RFC 4180](https://tools.ietf.org/html/rfc4180)標準に準拠したコンマ区切り値 (CSV) ファイルです。 ファイルは、変換を必要とせずに、Excel または他の標準規格に準拠したエディターで開くことができます。

CSV の最初の行には、列名が含まれています。

### <a name="fields-in-the-export"></a>エクスポートのフィールド

エクスポートされたファイルには、オンラインレポートでは使用できない追加のフィールドが含まれています。 これらは、トラブルシューティングや自動化されたワークフローに使用できます。

> [!div class="has-no-wrap"]  
> | #  | 名前 | [データ型 (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | 説明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | この Id | `uniqueidentifier` | 一意の通話識別子 |
> | 1 | 通話 ID | `nvarchar(64)` | 通話識別子。 一意であるとは限りません |
> | 2 | 会議 ID | `nvarchar(64)` | 電話会議の ID |
> | 3 | ユーザーの場所 | `nvarchar(2)` | ユーザーの国コード、 [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Azure Active Directory でユーザーの ID を呼び出します。<br/> ボット通話の種類 (ucap_in、ucap_out) については、この情報とその他のユーザー情報は null または空になります。 |
> | 5 | UPN | `nvarchar(128)` | Azure Active Directory での UserPrincipalName (サインイン名)。<br/>通常、これはユーザーの SIP アドレスと同じであり、ユーザーのメールアドレスと同じにすることができます。 |
> | 6 | ユーザーの表示名 | `nvarchar(128)` | ユーザーの表示名 |
> | 7 | 発信者番号 | `nvarchar(128)` | 着信通話を受信した電話番号、または発信通話でダイヤルした番号。 [E.i](https://en.wikipedia.org/wiki/E.164)形式 |
> | 個 | 通話の種類 | `nvarchar(32)` | 通話が PSTN の送信または着信であるか、ユーザーまたは電話会議によって発信された通話などの通話の種類であるか |
> | ファイブ | 数値の種類 | `nvarchar(16)` | ユーザーの電話番号の種類 (無料番号のサービスなど) |
> | 常用 | 国内/国際 | `nvarchar(16)` | ユーザーの所在地に基づいて、通話が国内 (国または地域内) または国際 (国または地域外) のどちらであったか |
> | 折り | ダイヤル先 | `nvarchar(64)` | ダイヤル先の国または地域 |
> | 以内 | 通話先の電話番号 | `nvarchar(32)` | 番号が[164](https://en.wikipedia.org/wiki/E.164)形式でダイヤルされる |
> | 14 | 開始時刻 | `datetimeoffset` | 通話開始時刻 (UTC、 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 14 | 終了時刻 | `datetimeoffset` | 通話終了時刻 (UTC、 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | マート | 継続時間 (秒) | `int` | 通話が接続されていた時間 |
> | 16 | 接続料金 | `numeric(16, 2)` | 接続料金 |
> | 18 | 職責 | `numeric(16, 2)` | お客さまのアカウントに課金される金額または通話の料金 |
> | 才 | 通貨 | `nvarchar(3)` | 通話の料金を計算するために使用される通貨の種類 ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | # | 機能 | `nvarchar(32)` | 通話に使用されたライセンス |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype For business 電話会議開催者アクティビティレポート](conference-organizer-activity-report.md)IM、音声/ビデオ、アプリケーション共有、Web、/ダイヤルアウト-サードパーティ、およびダイヤルアウト-Microsoft を使用して、ユーザーが会議をどの程度管理しているかを確認できます。
    
- [Skype For business 電話会議参加者アクティビティレポート](conference-participant-activity-report.md)IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルアウト音声会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype For business ユーザーがブロック](users-blocked-report.md)されたレポートPSTN 通話の発信をブロックされている組織内のユーザーを確認できます。

- [Skype For BUSINESS PSTN 分単位のプールレポート](pstn-minute-pools-report.md)には、組織内の現在の月に消費された分数が表示されます。

- [Skype For business セッションの詳細レポート](session-details-report.md)個々のユーザの通話エクスペリエンスについての詳細を見ることができます。
    
## <a name="related-topics"></a>関連項目
[管理センターでのアクティビティレポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
