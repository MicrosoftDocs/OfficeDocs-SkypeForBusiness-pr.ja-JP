---
title: '[通話の詳細の記録] と [エクスペリエンスの品質] の設定を構成Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '概要: CDR と QoE を構成する方法についてSkype for Business Server。'
ms.openlocfilehash: 5e04ac3fcf269ba9520e874e123f165f2fd4269a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604236"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>[通話の詳細の記録] と [エクスペリエンスの品質] の設定を構成Skype for Business Server
 
**概要:** CDR と QoE を構成する方法については、Skype for Business Server。
  
CDR と QoE の監視を、SQL Server Reporting Servicesレポートを使用してSkype for Business Server。
  
## <a name="configure-cdr-and-qoe"></a>CDR と QoE の構成

監視ストアをフロントエンド プールに関連付け、監視ストアをセットアップし、SQL Server Reporting Services と監視レポートをインストールして構成した後、Skype for Business Server 管理シェルを使用して通話詳細記録 (CDR) および QoE (QoE) 監視を管理できます。 Skype for Business Server管理シェルコマンドレットを使用すると、特定のサイトまたはサイト全体の CDR および QoE 監視を有効またはSkype for Business Serverできます。これは、次のように簡単なコマンドで実行できます。
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

サーバーをインストールSkype for Business Server、CDR と QoE の両方のグローバル構成設定の定義済みのコレクションもインストールします。 以下の表に、通話詳細記録で比較的よく使用される一部の設定の既定値を示します。
  
|**プロパティ**|**説明**|**既定値**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |CDR が有効かどうかを示します。True の場合、すべての CDR レコードが収集され、監視データベースに書き込まれます。  <br/> |正解  <br/> |
|EnablePurging  <br/> |CDR レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepCallDetailForDays プロパティ (CDR レコードの場合) および KeepErrorReportForDays プロパティ (CDR エラーの場合) で指定されている期間を過ぎると、レコードが削除されます。False の場合、CDR レコードは無期限に保持されます。  <br/> |正解  <br/> |
|KeepCallDetailForDays  <br/> |CDR レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。  <br/> KeepCallDetailForDays には、1 ～ 2,562 (約 7 年間の日数に相当) の範囲の任意の整数値を設定できます。  <br/> |60 (日)  <br/> |
|KeepErrorReportForDays  <br/> |CDR エラー レポートが保持される日数を示します。指定した日数より古いレポートは自動的に削除されます。 CDR エラー レポートは、クライアント アプリケーションによってアップロードされた診断レポートです (Skype for Business Server)。  <br/> このプロパティには、1 ～ 2,562 (日) の範囲の任意の整数値に指定できます。  <br/> |60 (日)  <br/> |
   
同様に、一部の QoE 設定の既定値を以下の表に示します。
  
|**プロパティ**|**説明**|**既定値**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |QoE 監視が有効かどうかを示します。True の場合、すべての QoE レコードが収集され、監視データベースに書き込まれます。  <br/> |正解  <br/> |
|EnablePurging  <br/> |QoE レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepQoEDataForDays プロパティで指定されている期間を過ぎると、レコードが削除されます。False の場合、QoE レコードは無期限に保持されます。  <br/> |正解  <br/> |
|KeepQoEDataForDays  <br/> |QoE レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。  <br/> KeepCallDetailForDays は、1 ～ 2562 (日) の範囲の任意の整数値に設定できます。  <br/> |60 日  <br/> |
   
これらのグローバル設定を変更する必要がある場合は、このコマンドレットと Set-CsCdrConfigurationをSet-CsQoEConfigurationできます。 たとえば、このコマンド (Skype for Business Server管理シェル内から実行) は、グローバル スコープでの CDR 監視を無効にします。EnableCDR プロパティを False (既定の値) に設定$False。
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

監視を無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されず、バックエンド監視データベースがアンインストールされたり、その他の影響がこのデータベースに及んだりすることもありません。 Skype for Business Server管理シェルを使用して CDR または QoE の監視を無効にした場合、実際に行うのは、監視データの収集とアーカイブSkype for Business Server一時的に停止することです。 この場合、次のように EnableCDR プロパティの設定を True ($True) に戻すだけで、CDR データの収集とアーカイブを再開できます。
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

同様に、次のコマンドは、QoE レコードの削除をグローバル スコープで無効にします。
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

CDR と QoE の構成設定は、グローバル設定だけでなく、サイト スコープに割り当てることもできます。これにより、監視についての管理の柔軟性が向上します。たとえば、管理者は Redmond サイトで CDR 監視を有効にする一方で Dublin サイトでは CDR 監視を無効にできます。新しい CDR 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

サイト スコープで構成されたこの設定は、グローバル スコープで構成された設定よりも優先されることに注意してください。たとえば、CDR 監視がグローバル スコープで有効になっていても、サイト スコープ (Redmond サイト) では無効になっているとします。この場合、Redmond サイト内のユーザーについては通話詳細記録の情報がアーカイブされません。ただし、その他のサイト内のユーザー (つまり、Redmond サイトの設定ではなくグローバル設定によって管理されているユーザー) の通話詳細記録の情報はアーカイブされます。
  
新しい QoE 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

詳細については、管理シェル内から次のコマンドSkype for Business Server入力します。
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
