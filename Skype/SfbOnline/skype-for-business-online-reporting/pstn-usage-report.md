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
description: 新しい [管理Skype for Business レポート] 領域には、組織内の通話と電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、Skype for Business での PSTN 使用状況の詳細レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 電話会議の PSTN 使用状況の詳細 (通話のコストを含む) を表示して、使用状況を把握し、請求の詳細を呼び出して組織内の使用状況を判断できます。
ms.openlocfilehash: b806c0b3a471f862de6d69c6ed9b5220441c4257
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238205"
---
# <a name="pstn-usage-report"></a>PSTN の使用状況レポート

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

新しい [管理Skype for Business レポート]**領域** には、組織内での通話と電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、 **Skype for Business での PSTN 使用状況の詳細** レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 電話会議の PSTN 使用状況の詳細 (通話のコストを含む) を表示して、使用状況を把握し、請求の詳細を呼び出して組織内の使用状況を判断できます。
  
利用可能なその [他のレポートについては](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 、「レポートの概要」を参照してください。
  
このレポートは、他のレポートとSkype for Business、組織全体での使用状況の呼び出しなど、アクティビティの詳細を示します。 これらの詳細は、組織に対して調査、計画、その他のビジネス上の決定を行う場合や、通信クレジット を設定する場合に [非常に役立ちます](/microsoftteams/what-are-communications-credits)。
  
> [!NOTE]
> 管理者として管理センターにログオンSkype for Business、すべてのレポートをMicrosoft 365できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Skype for Business の PSTN 使用状況詳細レポートを取得する方法

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

- 管理センターに移動し、[管理センター>**管理センター Skype for Business**  >  **PSTN 使用状況**  >    >  **の詳細を報告します**。
    
    > [!NOTE]
    > サブスクリプションのMicrosoft 365またはOffice 365によっては、ここに表示される製品とレポートの一部が表示されない場合があります。
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Skype for Business PSTN 使用状況レポートを解析する

表示されている各列を見ると、ユーザーの Skype for Business PSTN 使用状況を確認できます。
  
レポートは、このように表示されます。
  
[![Skype for Business PSTN 使用状況レポートの作成 ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![数値 1](../images/sfbcallout1.png)<br/>この表は、ユーザーごとの、すべての PSTN 使用状況の詳細を示しています。また、Skype for Business が割り当てられているすべてのユーザーと、ユーザーの PSTN 使用状況を示しています。表では、列を追加したり、削除したりすることができます。
*    **通話 ID** は通話の識別番号です。 これは、Microsoft サービス サポートを呼び出す際に使用される呼び出しの識別子です。
*    [ **ユーザー ID**] は、ユーザーのサインイン名です。
*    **電話番号** は着信通話を受けた Skype for Business の電話番号、または発信通話でダイヤルされた番号です。
*    **ユーザーの** 場所は、ユーザーが位置する国/地域です。
*    **発信者 ID** は着信通話の発信者電話番号 (発信者 ID) であるか、通話の発信元の番号であるか、発信通話に対して通話の発信元となった Skype for Business 番号です。
*    **通話の** 種類は、通話が PSTN 発信通話か着信通話か、通話の種類 (ユーザーが発信した通話や音声会議など) かです。 表示される可能性のある通話の種類は次のとおりです。 

     **通話プランの通話の種類** 
     *    **user_in** (着信 PSTN 通話を受信したユーザー) 
     *    **user_out** (発信 PSTN 通話をかけたユーザー) 
     *    **user_out_conf** (2 つ以上の PSTN 参加者を 3 方向の電話会議などに追加したユーザー) 
     *    **user_out_transfer** (PSTN 番号に通話を転送したユーザー) 
     *    **user_out_forwarding** (PSTN 番号に通話を転送したユーザー)

     **電話会議の通話の種類**
     *    **conf_in** (電話会議ブリッジへの着信呼び出し)。 この通話の種類のレコードの場合、[ユーザー **ID]** 列で指定されたユーザーは会議の開催者に対応します。
     *    **conf_out** (電話会議ブリッジからの発信通話で、通常は PSTN 番号を会議に追加します)。 この通話の種類のレコードの場合、[ユーザー **ID]** 列で指定されたユーザーは会議の開催者に対応します。

     **統合コミュニケーション アプリケーション (UCAP)** 
     *    **ucap_in** (自動応答や通話キューなど、UC アプリケーションへの着信 PSTN 呼び出し) 
     *    **ucap_out** (自動応答や通話キューなど、UC アプリケーションからの発信 PSTN 通話)
         > [!NOTE]
         > 自動応答や通話キューなど、UC アプリケーションからユーザーに転送された通話は、PSTN 使用状況レポートには表示されません。これらの呼び出し脚はピアツーピア (P2P) 音声通話です。 Skype for Business 管理センターの [Tools > Skype for Business Call Analytics] で P2P 呼び出しにアクセスし、日付/時刻や発信元の CLID (呼び出し元の回線 ID) で呼び出しを関連付けるユーザー名または SIP アドレスで検索できます。 

     [ **国内/国際**] は、ユーザーの場所に基づいて通話が国内 (国/地域内) または国際 (国/地域外) のどちらと見なされるかを示します。 
*    **[ダイヤル先** ] は、フランス、ドイツ、米国 (米国) など、ダイヤルされる国/地域の宛先の名前です。 
*    **[電話番号** の種類] は、ユーザーの電話番号、サービス、または無料電話番号の電話番号の種類です。  
*    [ **開始時刻 (UTC)**] は、通話が開始または実行された時刻です。 
*    [ **通話時間**] は、通話が接続されていた時間です。  
*    **ConfID** は電話会議の電話会議 ID です。 
*    [ **料金**] は、アカウントに課金される金額または通話の料金です。 
*    [ **通貨**] は、通話の料金を計算するために使用される通貨の種類です。 
*    [ **機能** ] は通話のために使用されるライセンスです。表示されるライセンスの種類は次のとおりです。 
     *    **MCOPSTNPP** - コミュニケーション クレジット <br/> **MCOPSTN1** - 国内通話プラン (米国 3000 分/ EU 1200 分プラン) 
     *    **MCOPSTN2** - 国際通話プラン 
     *    **MCOPSTN5** - 国内通話プラン (120 分の通話プラン) 
     *    **MCOPSTN6** - 国内通話プラン (240 分通話プラン) 注: 制限付き可用性
     *    **MCOMEETADD** - 電話会議
     *    **MCOMEETACPEA** - 分単位の電話会議による支払い
     
> [!NOTE]
> 通話または会議サブスクリプションに含まれていない 1 分あたりの支払い通話のみを含めるレポートを実行する場合は、機能 "MCOPSTNPP" でレポートをフィルター処理します。 これにより、1 分あたりのすべての支払い呼び出しの明細が提供されます。  分単位の電話会議の場合は、"MCOPSTNPP" ではなく "MCOMEETACPEA" でフィルター処理します。  

> [!NOTE]
> 一部のフィールドに "データなし" が表示される場合があります。 "データなし" は、フィールドが呼び出しの種類または機能に適用できないという意味です。 

> [!NOTE]
> Telstra または Softbank 通話プランをお持ちである場合は、PSTN 利用状況レポートに通話の詳細レコードは表示されます。 レポートのニーズについては、Telstra または Softbank にお問い合わせください。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。
 ***

## <a name="exporting-pstn-usage-report"></a>PSTN 使用状況レポートのエクスポート

[エクスポート] ボタンをクリック **Excelタップすると**、PSTN 利用状況レポートをダウンロードできます。 国固有の規制で 12 か月間のデータの保持が禁止されていない限り、現在の日付から最大 1 年間データをエクスポートできます。

これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。

エクスポート プロセスは、データの量に応じて、完了まで数秒から数分かかる場合があります。 サーバーがエクスポートを完了すると、" Calls.Export.[ という名前の zip **ファイルを受信します。 `identifier`.zip、** 識別子がエクスポートの一意の ID で、トラブルシューティングに使用できます。

通話プランと直接ルーティングの両方がある場合、エクスポートされたファイルには両方の製品のデータが含まれている可能性があります。 PSTN 使用状況レポート ファイルには、ファイル名 "**PSTN.calls.[ ] があります `UTC date` 。.csv**". PSTN ファイルと直接ルーティング ファイルに加えて、アーカイブには""parameters.jsというファイルが含まれているほか、選択したエクスポート時間範囲と機能が含まれる (必要な場合)。

エクスポートされたファイルはコンマ区切り値 (CSV) ファイルで [、RFC 4180 標準に準拠](https://tools.ietf.org/html/rfc4180) しています。 変換を必要とせずに、Excelまたは他の標準に準拠したエディターでファイルを開くことができます。

CSV の最初の行には、列名が含まれている。

### <a name="fields-in-the-export"></a>エクスポートのフィールド

エクスポートされたファイルには、オンライン レポートで使用できない追加のフィールドが含まれています。 これらは、トラブルシューティングと自動化されたワークフローに使用できます。

> [!div class="has-no-wrap"]  
> | #  | 名前 | [データ型 (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | 説明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 一意の呼び出し識別子 |
> | 1 | 通話 ID | `nvarchar(64)` | 呼び出し識別子。 一意である保証はありません |
> | 2 | 会議 ID | `nvarchar(64)` | 音声会議の ID |
> | 3 | ユーザーの場所 | `nvarchar(2)` | ユーザーの国コード [、ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | 呼び出し元のユーザーの ID Azure Active Directory。<br/> ボット呼び出しの種類の場合、この情報と他のユーザー情報は null/空になります (ucap_in、ucap_out) |
> | 5 | UPN | `nvarchar(128)` | [UserPrincipalName] (サインイン名) をAzure Active Directory。<br/>これは通常、ユーザーの SIP アドレスと同じであり、ユーザーの電子メール アドレスと同じものにできます。 |
> | 6 | ユーザー表示名 | `nvarchar(128)` | ユーザーの表示名 |
> | 7 | 発信者番号 | `nvarchar(128)` | 着信呼び出しの呼び出しを受信した番号、または発信呼び出しでダイヤルされた番号。 [E.164](https://en.wikipedia.org/wiki/E.164) 形式 |
> | 8 | 通話の種類 | `nvarchar(32)` | 通話が PSTN 発信通話か着信通話か、通話の種類 (ユーザーが発信した通話や音声会議など) か |
> | 9 | 数値の種類 | `nvarchar(16)` | ユーザーの電話番号の種類 (無料電話番号のサービスなど) |
> | 10 | 国内/国際 | `nvarchar(16)` | ユーザーの場所に基づいて、通話が国内 (国内または地域内) または国際通話 (国または地域外) の場合 |
> | 11 | ダイヤル先 | `nvarchar(64)` | ダイヤルされた国または地域 |
> | 12 | 宛先番号 | `nvarchar(32)` | [E.164 形式でダイヤルされた](https://en.wikipedia.org/wiki/E.164)番号 |
> | 13 | 開始時刻 | `datetimeoffset` | 通話開始時刻 (UTC、ISO [8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | 終了時刻 | `datetimeoffset` | 通話終了時刻 (UTC、ISO [8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Duration Seconds | `int` | 通話が接続された期間 |
> | 16 | 接続料金 | `numeric(16, 2)` | 接続料金 |
> | 17 | 料金 | `numeric(16, 2)` | アカウントに請求される通話の金額またはコスト |
> | 18 | 通貨 | `nvarchar(3)` | 通話のコストを計算するために使用される通貨の種類[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | 機能 | `nvarchar(32)` | 通話に使用されるライセンス |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business開催者アクティビティ レポートの作成](conference-organizer-activity-report.md)IM、音声/ビデオ、アプリケーション共有、Web、/dial out - サードパーティ、/ダイヤルアウト - Microsoft を使用する会議をユーザーがどれだけ開催しているか確認できます。
    
- [Skype for Business参加者アクティビティ レポートの作成](conference-participant-activity-report.md)参加している IM、音声/ビデオ、アプリケーション共有、Web およびダイヤルアウト音声会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype for Businessブロックレポート](users-blocked-report.md)PSTN 通話がブロックされている組織内のユーザーを確認できます。

- [Skype for Business PSTN 分](pstn-minute-pools-report.md)プール レポートでは、組織内の当月に消費された分数を確認できます。

- [Skype for Business詳細レポート](session-details-report.md)個々のユーザーの通話エクスペリエンスに関する詳細を確認できます。
    
## <a name="related-topics"></a>関連トピック
[管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
