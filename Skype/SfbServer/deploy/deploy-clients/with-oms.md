---
title: OMS を使用した Skype Room Systems バージョン 2 の管理を展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: この資料では、マイクロソフトの運用管理スイートを使用して、エンド ・ ツー ・ エンドの統合された方法で Skype ルーム システム v2 のデバイスの管理を展開する方法について説明します。
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>OMS を使用した Skype Room Systems バージョン 2 の管理を展開する
 
この資料では、マイクロソフトの運用管理スイートを使用して、エンド ・ ツー ・ エンドの統合された方法で Skype ルーム システム v2 のデバイスの管理を展開する方法について説明します。 
  
Skype 会議室デバイスを管理するのに役立つ基本的なテレメトリを提供するように、Microsoft Operations Management Suite (OMS) を構成することができます。お使いの管理ソリューションでは、時間の経過とともに、デバイスのパフォーマンスのより詳細なビューを作成するために追加データや管理機能を購入できます。
  
高いレベルでは、次のタスクを実行する必要があります。
  
1. [OMS 管理のデバイスを構成する ](with-oms.md#config_devices)
    
2. [カスタム フィールドをマップする](with-oms.md#Custom_fields)
    
3. [OMS　での SRS v2 ビューを定義する](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a>デバイスの場所、機能、構成を検索して記録する
<a name="find_devices"> </a>

最初のステップは、システム内のすべての装置、機能と構成の詳細、およびその場所についての詳細なデータベースを作成することです。小規模から中規模の組織では、この作業はスプレッドシートを使用することで十分対処できるでしょう。より大規模な組織の場合は、資産管理ツールやサードパーティのサービスを検討する必要があるかもしれません。いずれにしても、それぞれのデバイスについて、場所と関連情報をすべて記録することが重要になります。
  
作業が完了したら、その情報を使用して、技術者を派遣したり、デバイスパッチやアップグレードを管理したりすることができます。
  
## <a name="configure-devices-for-oms-management"></a>OMS 管理のデバイスを構成する 
<a name="config_devices"> </a>

SRS の各デバイスの[接続の Windows Azure のログ分析サービス コンピューター](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)に指示に従います。
  
## <a name="configure-oms-to-collect-device-event-logs"></a>デバイスのイベント ログを収集するよう OMS を構成する
<a name="config_devices"> </a>

[ログ分析では、Windows イベント ログ データ ソース](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)にある手順を使用して、SRS のデバイスからのイベント ログを収集するために OMS を特別に構成する必要があります。 SRS イベント ログを選択するのには「Skype ルーム システム」は、すべての種類のオプションのボックスをチェックする必要があります: エラー、警告、および情報です。
  
## <a name="map-custom-fields"></a>カスタム フィールドをマップする
<a name="Custom_fields"> </a>

[OMS でビューを定義する SRS v2](with-oms.md#Views)で作成したタイルを使用するには、ビューのユーザー設定フィールドを作成する必要があります。 カスタム フィールドの作成の詳細については、[ログの分析でユーザー設定フィールド](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields)を参照してください。
  
OMS が自動的に追加、_CF、新しいフィールドを定義するとき、以下のマッピングを使用します。 
  
> [!IMPORTANT]
> すべての JSON フィールドおよび OMS フィールドでは大文字と小文字が区別されます。 
  
**カスタム フィールドのマッピング**

|**JSON フィールド**|**OMS ユーザー設定フィールド**|
|:-----|:-----|
|説明  <br/> |SRSEventDescription_CF  <br/> |
|ResourceState  <br/> |SRSResourceState_CF  <br/> |
|OperationName  <br/> |SRSOperationName_CF  <br/> |
|OperationResult  <br/> |SRSOperationResult_CF  <br/> |
|OS  <br/> |SRSOSVersion_CF  <br/> |
|OSVersion  <br/> |SRSOSLongVersion_CF  <br/> |
|Alias  <br/> |SRSAlias_CF  <br/> |
|表示名  <br/> |SRSDisplayName_CF  <br/> |
|AppVersion  <br/> |SRSAppVersion_CF  <br/> |
|IPv4Address  <br/> |SRSIPv4Address_CF  <br/> |
|IPv6Address  <br/> |SRSIPv6Address_CF  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a>OMS での SRS v2 ビューを定義する
<a name="Views"> </a>

データが収集され、カスタム フィールドがマップされると、OMS ビュー デザイナーを使用して SRS v2 イベントを監視するためのタイルを含んでいるダッシュボードを開発することができます。 ビュー デザイナーを使用して、次のタイルを作成するには、必要に応じて、[ログ分析機能でカスタム ビューを作成するビュー デザイナーの使用](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer)を参照してください。
  
### <a name="create-a-tile-that-shows-healthy-devices"></a>正常なデバイスを示すタイルを作成する

1. ケースを定義します。 
    
    このタイルは、最近 10 分間にハートビート メッセージを送信したすべてのデバイスを表示します。
    
2. グループ タイトルを割り当てます  
    
   ```
   SRS v2
   ```

3. 新しいグループ ボックスを選択します
    
4. タイルの凡例のテキストを追加します
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. タイルのクエリを入力します
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. リストのクエリを入力します
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. 列のタイトル名を定義します
    
   ```
   Display Name
   ```

8. 列のタイトルの値を定義します
    
   ```
   Last HB
   ```

9. ナビゲーションのクエリを入力します
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a>接続に関する問題があるデバイスを示すタイルを作成する

1. ケースを定義します。 
    
    このタイルは、最近　10 分間にハートビート メッセージを送信していないデバイスをすべて表示します。これらのデバイスでは、ネットワーク接続、Exchange の接続、Skype for Business の接続に問題が発生している可能性があります。
    
2. グループ タイトルを割り当てます  
    
   ```
   SRS v2
   ```

3. 新しいグループ ボックスを選択しません。 これは既にタイル 1 の作成時に済んでいるので、再び行う必要はありません。
    
4. タイルの凡例のテキストを追加します
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. タイルのクエリを入力します
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. リストのクエリを入力します
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. 列のタイトル名を定義します
    
   ```
   Device Name
   ```

8. 列のタイトルの値を定義します 
    
   ```
   Last HB
   ```

9. ナビゲーションのクエリを入力します
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a>ハードウェア エラーがあるデバイスを一覧表示する 

1. ケースを定義します。 
    
   このタイルには、最後の 10 分の 1 つまたは複数のハードウェア コンポーネントの問題を示すメッセージを送信するすべてのデバイスが表示されます。 
    
2. グループ タイトルを割り当てます 
    
   ```
   SRS v2
   ```

3. 新しいグループ ボックスを選択しません。 これは既にタイル 1 の作成時に済んでいるので、再び行う必要はありません。
    
4. タイルの凡例:  
    
   ```
   Devices with a Hardware Error
   ```

5. タイルのクエリ:
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. リストのクエリ:
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. 列のタイトル名:  
    
   ```
   Display Name
   ```

8. 列のタイトル名:  
    
   ```
   Last Error
   ```

9. ナビゲーションのクエリ:  
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a>アプリのエラーがあるデバイスを一覧表示する 

1. ケースを定義します。 
    
   このタイルは最近 10 分間に 1 つまたは複数のアプリ コンポーネントのエラーを報告したすべての SRS デバイスを表示します
    
2. グループ タイトルを割り当てます 
    
   ```
   SRS v2
   ```

3. 新しいグループ ボックスを選択しません。 これは既にタイル 1 の作成時に済んでいるので、再び行う必要はありません。
    
4. タイルの凡例:  
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. タイルのクエリ:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. リストのクエリ:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. 列のタイトル名:  
    
   ```
   Device Name
   ```

8. 列のタイトル名:  
    
   ```
   Last Error
   ```

9. ナビゲーションのクエリ:
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a>再起動を必要とするデバイスを一覧表示する

1. ケースを定義します。 
    
   このタイルは過去 24 時間以内に再起動したすべての SRS デバイスと、再起動の回数を表示します。
    
2. グループ タイトルを割り当てます 
    
  ```
  SRS v2
  ```

3. 新しいグループ ボックスを選択しません。 これは既にタイル 1 の作成時に済んでいるので、再び行う必要はありません。
    
4. タイルの凡例:  
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. タイルのクエリ:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. リストのクエリ:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. 列のタイトル名:  
    
   ```
   Display Name
   ```

8. 列のタイトル名:  
    
   ```
   Number of restarts
   ```

9. ナビゲーションのクエリ:  
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

これでビューの作成は完了です。現在利用できるアラートはすべてこれらの 1 つまたは複数のタイルで反映されます。
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="Views"> </a>

#### 

[OMS を使用して Skype ルーム システム v2 の管理を計画します。](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[OMS を使用して Skype ルーム システム v2 のデバイスを管理します。](../../manage/skype-room-systems-v2/oms.md)

