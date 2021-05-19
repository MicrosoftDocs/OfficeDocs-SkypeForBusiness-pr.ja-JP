---
title: PSTN の使用状況のレポート
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
description: 新しい Skype for Business 管理センター レポートの領域に、組織内の通話および電話会議のアクティビティが示されます。ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。たとえば、 Skype for Business での PSTN 使用状況の詳細レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。通話料金を含む、電話会議 PSTN 使用状況の詳細を表示することができるため、使用状況と通話請求の詳細を把握して、組織内の使用状況を見極めることができます。
ms.openlocfilehash: b806c0b3a471f862de6d69c6ed9b5220441c4257
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238205"
---
# <a name="pstn-usage-report"></a>PSTN の使用状況のレポート

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

新しい Skype for Business 管理センター **レポート** の領域には、組織内の通話および電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、 **Skype for Business での PSTN 使用状況の詳細** レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 通話料金を含む、電話会議 PSTN 使用状況の詳細を表示することができるため、使用状況と通話請求の詳細を把握して、組織内の使用状況を見極めることができます。
  
利用可能なその他のレポートについては、[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)を確認してください。
  
このレポートとその他の Skype for Business レポートでは、組織全体にわたる、通話使用状況を含むアクティビティの詳細がわかります。 これらの詳細は、組織のための調査、計画、その他のビジネスの意思決定を行うとき、および[コミュニケーション クレジット](/microsoftteams/what-are-communications-credits)の設定に非常に役立ちます。
  
> [!NOTE]
> Microsoft 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Skype for Business の PSTN 使用状況詳細レポートを取得する方法

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

- 管理センター > **[管理センター]** > **[Skype for Business 管理センター]** > **[レポート]** > **[PSTN 使用状況の詳細]** の順に移動します。
    
    > [!NOTE]
    > Microsoft 365 または Office 365 のサブスクリプションによっては、ここに表示される製品やレポートの一部が表示されないことがあります。
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Skype for Business PSTN 使用状況レポートを解析する

表示されている各列を見ると、ユーザーの Skype for Business PSTN 使用状況を確認できます。
  
レポートは、このように表示されます。
  
[ ![Skype for Business PSTN 使用状況レポート](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png) ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![番号 1](../images/sfbcallout1.png)<br/>この表は、ユーザーごとの、すべての PSTN 使用状況の詳細を示しています。また、Skype for Business が割り当てられているすべてのユーザーと、ユーザーの PSTN 使用状況を示しています。表では、列を追加したり、削除したりすることができます。
*    **通話 ID** は通話の通話 ID です。 Microsoft サービス サポートへの通話で使用される通話の識別子です。
*    [ **ユーザー ID**] は、ユーザーのサインイン名です。
*    **電話番号** は着信通話を受けた Skype for Business の電話番号、または発信通話でダイヤルされた番号です。
*    **ユーザーの所在地** は、ユーザーがいる国/地域です。
*    **発信者 ID** は着信通話の発信者電話番号 (発信者 ID) であるか、通話の発信元の番号であるか、発信通話に対して通話の発信元となった Skype for Business 番号です。
*    **通話の種類** は、通話が PSTN 発信通話であるか着信通話であるか、およびユーザーによってかけられた通話であるか電話会議であるかという通話の種類を示します。 表示される可能性のある通話の種類は次のとおりです。 

     **通話プランの通話の種類** 
     *    **user_in** (着信 PSTN 通話を受信したユーザー) 
     *    **user_out** (発信 PSTN 通話をかけたユーザー) 
     *    **user_out_conf** (2 つ以上の PSTN 参加者を 3 方向の電話会議などに追加したユーザー) 
     *    **user_out_transfer** (PSTN 番号に通話を転送したユーザー) 
     *    **user_out_forwarding** (PSTN 番号に通話を転送したユーザー)

     **電話会議の通話の種類**
     *    **conf_in** (電話会議ブリッジへの受信通話)。 この通話の種類のレコードの場合、**[ユーザー ID]** 列で指定されたユーザーは、会議の開催者に対応します。
     *    **conf_out** (通常は電話会議に PSTN 番号を追加するための電話会議ブリッジからの発信通話)。 この通話の種類のレコードの場合、**[ユーザー ID]** 列で指定されたユーザーは、会議の開催者に対応します。

     **統合コミュニケーション アプリケーション (UCAP)** 
     *    **ucap_in** (自動応答や通話キューなどの UC アプリケーションへの PSTN 受信通話) 
     *    **ucap_out** (自動応答や通話キューなどの UC アプリケーションからの PSTN 発信通話)
         > [!NOTE]
         > 自動応答や通話キューなどの UC アプリケーションからユーザーに転送された通話は、これらの通話レッグがピア ツー ピア (P2P) オーディオ通話であるため、PSTN 使用状況レポートに表示されません。 Skype for Business 管理センターの [ツール] > [Skype for Business 通話分析] で P2P 通話にアクセスし、日付/時刻や発信元の CLID (発信回線 ID) で通話を関連付けるユーザー名または SIP アドレスで検索できます。 

     [ **国内/国際**] は、ユーザーの場所に基づいて通話が国内 (国/地域内) または国際 (国/地域外) のどちらと見なされるかを示します。 
*    [**ダイヤル先**] は、フランス、ドイツ、米国 (U.S.) など、ダイヤルされる国/地域の宛先の名前です。 
*    [**番号の種類**] は、ユーザーの電話番号、サービス、またはフリーダイヤルからの電話番号の種類です。  
*    [ **開始時刻 (UTC)**] は、通話が開始または実行された時刻です。 
*    [ **通話時間**] は、通話が接続されていた時間です。  
*    **ConfID** は電話会議の電話会議 ID です。 
*    [ **料金**] は、アカウントに課金される金額または通話の料金です。 
*    [ **通貨**] は、通話の料金を計算するために使用される通貨の種類です。 
*    [ **機能** ] は通話のために使用されるライセンスです。表示されるライセンスの種類は次のとおりです。 
     *    **MCOPSTNPP** - コミュニケーション クレジット <br/> **MCOPSTN1** - 国内通話プラン (米国では 3000 分 / EU では 1200 分のプラン) 
     *    **MCOPSTN2** - 国際通話プラン 
     *    **MCOPSTN5** - 国内通話プラン (120 分通話プラン) 
     *    **MCOPSTN6** - 国内通話プラン (240 分通話プラン) 注: 限られた可用性
     *    **MCOMEETADD** - 電話会議
     *    **MCOMEETACPEA** - 分数ごと従量課金制電話会議
     
> [!NOTE]
> 通話または会議のサブスクリプションに含まれていない分数ごと従量課金制通話のみを含むようにレポートを実行する場合は、機能 "MCOPSTNPP" でレポートをフィルター処理します。 そうすることで、すべての分数ごと従量課金制通話の明細が提供されます。  分数ごと従量課金制電話会議の場合は、"MCOPSTNPP" ではなく "MCOMEETACPEA" でフィルター処理します。  

> [!NOTE]
> 一部のフィールドに "データなし" と表示される場合もあります。 "データなし" は、フィールドが通話の種類または機能に適用されないことを意味します。 

> [!NOTE]
> Telstra または Softbank の通話プランをご利用の場合、PSTN 使用状況レポートに通話の詳細な記録が表示されません。 レポートが必要な場合は、Telstra または Softbank にお問い合わせください。 
***
![番号 2](../images/sfbcallout2.png)<br/>1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。
 ***

## <a name="exporting-pstn-usage-report"></a>PSTN 使用状況レポートのエクスポート

**[Excel にエクスポートする]** ボタンをクリックまたはタップすると、PSTN 使用状況レポートをダウンロードできます。 データのエクスポートは、各国の規制で 12 か月間の保持が禁止されている場合を除き、現在の日付から 1 年間行うことができます。

これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。

エクスポート処理は、データの量にもよりますが、数秒から数分で完了します。 サーバーがエクスポートを完了すると、"**Calls.Export.[`identifier`].zip**" という名前の zip ファイルを受信します。その識別子はトラブルシューティングに使用できるエクスポート用の一意の ID です。

通話プランとダイレクト ルーティングの両方を使用している場合、エクスポートされたファイルには両方の製品のデータが含まれている場合があります。 PSTN 使用状況レポート ファイルのファイル名は "**PSTN.calls.[`UTC date`].csv**" になります。 アーカイブには、PSTN およびダイレクト ルーティングのファイルに加えて、選択されたエクスポート時間範囲と機能 (存在する場合) を持つファイル "**parameters.json**" が含まれています。

エクスポートされるファイルは、[RFC 4180](https://tools.ietf.org/html/rfc4180) 規格に準拠したコンマ区切り値 (CSV) ファイルです。 このファイルは、変換を必要とせず、Excel やその他の標準に準拠したエディターで開くことができます。

CSV の 1 行目には列名が含まれます。

### <a name="fields-in-the-export"></a>エクスポートのフィールド

エクスポートされたファイルには、オンライン レポートでは利用できない追加フィールドが含まれています。 これらは、トラブルシューティングや自動化されたワークフローに利用できます。

> [!div class="has-no-wrap"]  
> | #  | 名前 | [データ型 (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | 説明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 一意の通話識別子 |
> | 1 | 通話 ID | `nvarchar(64)` | 通話識別子。 一意であることは保証されていません |
> | 2 | 電話会議 ID | `nvarchar(64)` | 電話会議の ID |
> | 3 | ユーザーの所在地 | `nvarchar(2)` | ユーザーの国コード、[ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Azure Active Directory 内の通話ユーザーの ID。<br/> ボット通話の種類 (ucap_in、ucap_out) では、このユーザー情報やその他のユーザー情報は、null/empty となります |
> | 5 | UPN | `nvarchar(128)` | Azure Active Directory での UserPrincipalName (サインイン名)。<br/>これは通常、ユーザーの SIP アドレスと同じですが、ユーザーのメール アドレスと同じにすることもできます |
> | 6 | ユーザーの表示名 | `nvarchar(128)` | ユーザーの表示名 |
> | 7 | 発信者 ID | `nvarchar(128)` | 着信通話を受けた Skype for Business の電話番号、または発信通話でダイヤルされた番号です。 [E.164](https://en.wikipedia.org/wiki/E.164) 形式 |
> | 8 | 通話の種類 | `nvarchar(32)` | 通話が PSTN 発信通話であるか着信通話であるか、およびユーザーによってかけられた通話であるか電話会議であるかという種類を示します |
> | 9 | 電話番号の種類 | `nvarchar(16)` | フリーダイヤルのサービスなど、ユーザーの電話番号の種類 |
> | 10 | 国内/国際 | `nvarchar(16)` | ユーザーの位置情報をもとに、その通話が国内 (国や地域内) のものか、国際 (国や地域外) のものかがわかります |
> | 11 | ダイヤル先 | `nvarchar(64)` | ダイヤルした国または地域 |
> | 12 | 転送先番号 | `nvarchar(32)` | [E.164](https://en.wikipedia.org/wiki/E.164) 形式でダイヤルした番号 |
> | 13 | 開始時刻 | `datetimeoffset` | 通話開始時刻 (UTC、[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 14 | 終了時刻 | `datetimeoffset` | 通話終了時刻 (UTC、[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)) |
> | 15 | 通話時間 (秒) | `int` | 通話が接続されていた時間 |
> | 16 | 接続料金 | `numeric(16, 2)` | 接続料金の価格 |
> | 17 | 通話料 | `numeric(16, 2)` | アカウントに課金される金額または通話の料金 |
> | 18 | 通貨 | `nvarchar(3)` | 通話のコストを計算するために使用される通貨の種類です ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | 機能 | `nvarchar(32)` | 通話のために使用されるライセンス |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) - ユーザーが、IM、音声/ビデオ、アプリケーション共有、Web、/ダイヤルアウト - サードパーティ、/ダイヤルアウト - Microsoftを使用する会議をどの程度組織しているかを確認できます。
    
- [Skype for Business 電話会議参加者アクティビティ レポート](conference-participant-activity-report.md) - 参加している IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルアウト電話会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype for Business ユーザーのブロック レポート](users-blocked-report.md) - PSTN 通話の発信がブロックされている組織内のユーザーを確認できます。

- [Skype for Business PSTN の利用分数プール レポート](pstn-minute-pools-report.md) - 組織内で今月中に消費された分数を確認できます。

- [Skype for Business セッションの詳細レポート](session-details-report.md) - 個々のユーザーの通話体験に関する詳細を確認できます。
    
## <a name="related-topics"></a>関連トピック
[管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
