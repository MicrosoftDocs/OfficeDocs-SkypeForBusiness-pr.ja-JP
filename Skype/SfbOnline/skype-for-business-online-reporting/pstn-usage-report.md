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
description: 新しい Skype for Business 管理センターレポート領域には、組織内での通話と電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、Skype for Business での PSTN 使用状況の詳細レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 電話会議の PSTN 使用状況の詳細 (通話の料金など) を表示して、使用状況と通話請求の詳細を把握し、組織内の使用状況を判断できます。
ms.openlocfilehash: 831c1e7168bcffc72acb8ef1573167fe63ff44f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106473"
---
# <a name="pstn-usage-report"></a>PSTN の使用状況レポート

新しい Skype for Business 管理センター **レポート領域** には、組織内での通話と電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、 **Skype for Business での PSTN 使用状況の詳細** レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 通話の料金を含む電話会議 PSTN 使用状況の詳細を表示して、使用状況と通話請求の詳細を把握し、組織内の使用状況を判断することができます。
  
利用可能なその [他のレポートについては](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 、レポートの概要を確認してください。
  
このレポートは、他の Skype for Business レポートと共に、組織全体での通話の使用状況を含むアクティビティの詳細を示します。 これらの詳細は、組織のその他のビジネス上の決定を調査、計画、実行し、コミュニケーション クレジットを設定する場合に [非常に役立ちます](/microsoftteams/what-are-communications-credits)。
  
> [!NOTE]
> 管理者として Microsoft 365 管理センターにログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Skype for Business の PSTN 使用状況詳細レポートを取得する方法

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

- 管理センターに移動し、>   >  **Skype for Business 管理センターで** PSTN 使用状況  >    >  **の詳細を報告します**。
    
    > [!NOTE]
    > Microsoft 365 または Office 365 サブスクリプションによっては、ここに表示される製品やレポートの一部が表示されない場合があります。
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Skype for Business PSTN 使用状況レポートを解析する

表示されている各列を見ると、ユーザーの Skype for Business PSTN 使用状況を確認できます。
  
レポートは、このように表示されます。
  
[![Skype for Business PSTN 使用状況レポート ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![数値 1](../images/sfbcallout1.png)<br/>この表は、ユーザーごとの、すべての PSTN 使用状況の詳細を示しています。また、Skype for Business が割り当てられているすべてのユーザーと、ユーザーの PSTN 使用状況を示しています。表では、列を追加したり、削除したりすることができます。
*    **通話 ID** は通話の識別番号です。 これは、Microsoft サービス サポートを呼び出す際に使用される通話の識別子です。
*    [ **ユーザー ID**] は、ユーザーのサインイン名です。
*    **電話番号** は着信通話を受けた Skype for Business の電話番号、または発信通話でダイヤルされた番号です。
*    **ユーザーの** 場所は、ユーザーが保存されている国/地域です。
*    **発信者 ID** は着信通話の発信者電話番号 (発信者 ID) であるか、通話の発信元の番号であるか、発信通話に対して通話の発信元となった Skype for Business 番号です。
*    **通話の** 種類は、通話が PSTN 発信通話か着信通話か、ユーザーが発信した通話や音声会議などの通話の種類です。 表示される可能性のある通話の種類は次のとおりです。 

     **通話プランの通話の種類** 
     *    **user_in** (着信 PSTN 通話を受信したユーザー) 
     *    **user_out** (発信 PSTN 通話をかけたユーザー) 
     *    **user_out_conf** (2 つ以上の PSTN 参加者を 3 方向の電話会議などに追加したユーザー) 
     *    **user_out_transfer** (PSTN 番号に通話を転送したユーザー) 
     *    **user_out_forwarding** (PSTN 番号に通話を転送したユーザー)

     **電話会議の通話の種類**
     *    **conf_in** (電話会議ブリッジへの着信通話)。 この通話の種類のレコードの場合、[ユーザー **ID]** 列に指定されたユーザーは、会議の開催者に対応します。
     *    **conf_out** (電話会議ブリッジからの発信通話で、通常は PSTN 番号を会議に追加します)。 この通話の種類のレコードの場合、[ユーザー **ID]** 列に指定されたユーザーは、会議の開催者に対応します。

     **統合コミュニケーション アプリケーション (UCAP)** 
     *    **ucap_in** (自動応答や通話キューなどの UC アプリケーションへの受信 PSTN 通話) 
     *    **ucap_out** (自動応答や通話キューなどの UC アプリケーションからの発信 PSTN 通話)
         > [!NOTE]
         > 自動応答や通話キューなど、UC アプリケーションからユーザーに転送された通話は、PSTN 使用状況レポートには表示されません。これらの呼び出し呼び出しはピアツーピア (P2P) 音声通話です。 Skype for Business 管理センターの [ツール > Skype for Business 通話分析] で P2P 通話にアクセスし、日付/時刻や発信元の CLID (通話回線 ID) で呼び出しを関連付けるユーザー名または SIP アドレスで検索することができます。 

     [ **国内/国際**] は、ユーザーの場所に基づいて通話が国内 (国/地域内) または国際 (国/地域外) のどちらと見なされるかを示します。 
*    **ダイヤル先は** 、フランス、ドイツ、米国 (米国) など、ダイヤルされる国/地域の宛先の名前です。 
*    **電話番号の** 種類は、ユーザーの電話番号、サービス、または無料電話番号からの電話番号の種類です。  
*    [ **開始時刻 (UTC)**] は、通話が開始または実行された時刻です。 
*    [ **通話時間**] は、通話が接続されていた時間です。  
*    **ConfID** は電話会議の電話会議 ID です。 
*    [ **料金**] は、アカウントに課金される金額または通話の料金です。 
*    [ **通貨**] は、通話の料金を計算するために使用される通貨の種類です。 
*    [ **機能** ] は通話のために使用されるライセンスです。表示されるライセンスの種類は次のとおりです。 
     *    **MCOPSTNPP** - コミュニケーション クレジット <br/> **MCOPSTN1** - 国内通話プラン (米国 3000 分/ EU 1200 分プラン) 
     *    **MCOPSTN2** - 国際通話プラン 
     *    **MCOPSTN5** - 国内通話プラン (120 分通話プラン) 
     *    **MCOPSTN6** - 国内通話プラン (240 分通話プラン) 注: 限られた利用可能時間
     *    **MCOMEETADD** - 電話会議
     *    **MCOMEETACPEA** - 分単位の電話会議の支払い
     
> [!NOTE]
> 通話または会議サブスクリプションに含まれていない 1 分あたりの支払いのみを含めるレポートを実行する場合は、機能 "MCOPSTNPP" でレポートをフィルター処理します。 これにより、1 分あたりのすべての支払い通話の項目化が提供されます。  分単位の電話会議の場合は、"MCOPSTNPP" の代わりに "MCOMEETACPEA" でフィルター処理します。  

> [!NOTE]
> 一部のフィールドに "データなし" と表示される場合があります。 "データなし" は、フィールドが通話の種類または機能に適用されないという意味です。 

> [!NOTE]
> Telstra または Softbank 通話プランをお持ちである場合は、PSTN 使用状況レポートに通話詳細レコードは表示されない。 レポートのニーズについては、Telstra または Softbank にお問い合わせください。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。
 ***

## <a name="exporting-pstn-usage-report"></a>PSTN 使用状況レポートのエクスポート

[Excel にエクスポート] **ボタンを** クリックまたはタップすると、PSTN 使用状況レポートをダウンロードできます。 国固有の規制で 12 か月間のデータの保持が禁止されていない限り、現在の日付から最大 1 年のデータをエクスポートできます。

これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。

エクスポート プロセスは、データの数量に応じて、数秒から数分で完了します。 サーバーがエクスポートを完了すると、"Calls.Export.[ ]" という名前の zip **ファイルを受信 `identifier` します。zip**"。識別子はエクスポートの一意の ID で、トラブルシューティングに使用できます。

通話プランと直接ルーティングの両方がある場合、エクスポートされたファイルには両方の製品のデータが含まれている可能性があります。 PSTN 使用状況レポート ファイルには、ファイル名 "**PSTN.calls.[ `UTC date` ]があります。csv**". PSTN ファイルと直接ルーティング ファイルに加えて、アーカイブには"**ファイル"** parameters.jsが含まれるので、選択したエクスポート時間の範囲と機能 (必要な場合) が含まれる。

エクスポートされるファイルは、RFC [4180](https://tools.ietf.org/html/rfc4180) 標準に準拠したコンマ区切り値 (CSV) ファイルです。 変換を必要とせずに、Excel または他の標準に準拠したエディターでファイルを開くことができます。

CSV の最初の行には列名が含まれている。

### <a name="fields-in-the-export"></a>エクスポートのフィールド

エクスポートされたファイルには、オンライン レポートで使用できない追加のフィールドが含まれています。 これらは、トラブルシューティングや自動ワークフローに使用できます。

> [!div class="has-no-wrap"]  
> | #  | 名前 | [データ型 (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | 説明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 一意の呼び出し識別子 |
> | 1 | 通話 ID | `nvarchar(64)` | 呼び出し識別子。 一意である保証はありません |
> | 2 | 会議 ID | `nvarchar(64)` | 音声会議の ID |
> | 3 | ユーザーの場所 | `nvarchar(2)` | ユーザーの国コード [、ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Azure Active Directory でのユーザー ID の呼び出し。<br/> この情報と他のユーザー情報は、ボットの通話の種類 (ucap_in、ucap_out) の場合は null または空になります。 |
> | 5 | UPN | `nvarchar(128)` | Azure Active Directory の UserPrincipalName (サインイン名)。<br/>これは通常、ユーザーの SIP アドレスと同じであり、ユーザーのメール アドレスと同じものにできます。 |
> | 6 | ユーザー表示名 | `nvarchar(128)` | ユーザーの表示名 |
> | 7 | 発信者番号 | `nvarchar(128)` | 着信通話の呼び出しを受けた番号、または発信通話にダイヤルされた番号。 [E.164 形式](https://en.wikipedia.org/wiki/E.164) |
> | 8 | 通話の種類 | `nvarchar(32)` | 通話が PSTN 発信通話か着信通話か、ユーザーが発信した通話や音声会議などの通話の種類 |
> | 9 | 数値の種類 | `nvarchar(16)` | ユーザーの電話番号の種類 (無料電話番号のサービスなど) |
> | 10 | 国内/国際 | `nvarchar(16)` | ユーザーの場所に基づいて、通話が国内 (国または地域内) か国際 (国または地域外) か |
> | 11 | ダイヤル先 | `nvarchar(64)` | ダイヤルされた国または地域 |
> | 12 | 宛先番号 | `nvarchar(32)` | [E.164 形式でダイヤルされた](https://en.wikipedia.org/wiki/E.164)番号 |
> | 13 | 開始時刻 | `datetimeoffset` | 通話開始時刻 (UTC、ISO [8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | 終了時刻 | `datetimeoffset` | 通話終了時刻 (UTC、ISO [8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Duration Seconds | `int` | 通話が接続された期間 |
> | 16 | 接続料金 | `numeric(16, 2)` | 接続料金 |
> | 17 | 充電 | `numeric(16, 2)` | アカウントに請求される通話の金額またはコスト |
> | 18 | 通貨 | `nvarchar(3)` | 通話のコストを計算するために使用される通貨の種類[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | 機能 | `nvarchar(32)` | 通話に使用されるライセンス |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) IM、音声/ビデオ、アプリケーション共有、Web、/ダイヤルアウト - サードパーティ、/ダイヤルアウトを使用する電話会議をユーザーがどれだけ開催しているかは、Microsoft で確認できます。
    
- [Skype for Business 電話会議参加者アクティビティ レポート](conference-participant-activity-report.md) 参加している IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルアウト音声会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype for Business ユーザーのブロックレポート](users-blocked-report.md) PSTN 通話がブロックされている組織内のユーザーを確認できます。

- [Skype for Business PSTN ミニサイト プール](pstn-minute-pools-report.md) レポートでは、組織内の今月の使用分数を確認できます。

- [Skype for Business セッションの詳細レポート](session-details-report.md) 個々のユーザーの通話エクスペリエンスに関する詳細を確認できます。
    
## <a name="related-topics"></a>関連項目
[管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
