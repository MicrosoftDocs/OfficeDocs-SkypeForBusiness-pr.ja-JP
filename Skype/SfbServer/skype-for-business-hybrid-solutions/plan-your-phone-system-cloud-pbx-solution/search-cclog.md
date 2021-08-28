---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: このSearch-CcLogコマンドレットは、アプライアンス ログ ディレクトリ内の着信および発信Skype for Business クラウド コネクタ エディションを検索します。
ms.openlocfilehash: b96e0bea7c8a7ac9d3a12c135c828440eea9fb32
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618693"
---
# <a name="search-cclog"></a>Search-CcLog
 
このSearch-CcLogコマンドレットは、アプライアンス ログ ディレクトリ内の着信および発信Skype for Business クラウド コネクタ エディションを検索します。
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、既定のファイル名を使用して、アプライアンス ログ ディレクトリ内の着信および発信通話ログを検索します。
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>例 2

次の使用例は、指定されたファイル パスと名前を使用して着信および発信通話ログを検索します。
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Search-CsClsLogging コマンドレットは、集中ログ サービスが生成したログ ファイルを検索するためのコマンドライン オプションを提供します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | 必須 <br/> |System.Datetime  <br/> | 検索対象のログ エントリの開始日時です。 現地のタイム ゾーンで指定します。 <br/> |
|EndTime  <br/> |必須  <br/> |System.Datetime  <br/> |検索対象のログ エントリの終了日時です。 現地のタイム ゾーンで指定します。  <br/> |
|FileName  <br/> |必須  <br/> |System.String  <br/> |検索結果を含むテキスト ファイルの完全なパスを指定します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このSearch-CcLogは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

