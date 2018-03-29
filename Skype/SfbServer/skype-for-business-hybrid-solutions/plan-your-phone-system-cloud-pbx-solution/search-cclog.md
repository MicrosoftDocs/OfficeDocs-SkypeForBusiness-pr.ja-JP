---
title: 検索 CcLog
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Search-CcLog コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンス ログ ディレクトリで着信および発信の通話ログを検索します。
ms.openlocfilehash: 3d7d34f2e069b9c4ed728dcc805af5ccf9d13067
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="search-cclog"></a>検索 CcLog
 
Search-CcLog コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンス ログ ディレクトリで着信および発信の通話ログを検索します。
  
```
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、着信を検索し、既定のファイル名を使用してアプライアンス ・ ログ ・ ディレクトリに発信呼び出しをログに記録します。
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>例 2

次の例では、所定のファイル パスと名前を使用して着信および発信の通話ログを検索します。
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Search-CsClsLogging コマンドレットは、集中ログ サービスが生成したログ ファイルを検索するためのコマンドライン オプションを提供します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
|開始時刻  <br/> | 必須 <br/> |System.Datetime  <br/> | 検索対象のログ エントリの開始日時です。現地のタイム ゾーンで指定します。 <br/> |
|終了時刻  <br/> |必須  <br/> |System.Datetime  <br/> |検索対象のログ エントリの終了日時です。現地のタイム ゾーンで指定します。  <br/> |
|ファイル名  <br/> |必須  <br/> |System.String  <br/> |検索結果を含むテキスト ファイルの完全なパスを指定します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Search-CcLog コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[開始 CcLogging](start-cclogging.md)
  
[Stop CcLogging](stop-cclogging.md)
  

