---
title: Skype for Business Server で通話詳細記録と Quality of Experience の設定を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '概要: Skype for Business Server で CDR と QoE を構成する方法について学習します。'
ms.openlocfilehash: dd8611723e3d83f8a4553ba2148ee5ae29791e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802287"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Skype for Business Server で通話詳細記録と Quality of Experience の設定を構成する
 
**概要:** Skype for Business Server で CDR と QoE を構成する方法について学習します。
  
Skype for Business Server の Reporting Services SQL Serverを使用して CDR および QoE 監視を構成します。
  
## <a name="configure-cdr-and-qoe"></a>CDR と QoE を構成する

監視ストアをフロントエンド プールに関連付け、監視ストアをセットアップし、SQL Server Reporting Services および監視レポートをインストールして構成したら、Skype for Business Server 管理シェルを使用して通話詳細記録 (CDR) および QoE (Quality of Experience) 監視を管理できます。 Skype for Business Server 管理シェル コマンドレットを使用すると、特定のサイトまたは Skype for Business Server 展開全体に対して CDR および QoE 監視を有効または無効にできます。これは、次のように簡単なコマンドで実行できます。
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Skype for Business Server をインストールすると、CDR と QoE の両方のグローバル構成設定の定義済みコレクションもインストールされます。 以下の表に、通話詳細記録で比較的よく使用される一部の設定の既定値を示します。
  
|**プロパティ**|**説明**|**既定値**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |CDR が有効かどうかを示します。True の場合、すべての CDR レコードが収集され、監視データベースに書き込まれます。  <br/> |正  <br/> |
|EnablePurging  <br/> |CDR レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepCallDetailForDays プロパティ (CDR レコードの場合) および KeepErrorReportForDays プロパティ (CDR エラーの場合) で指定されている期間を過ぎると、レコードが削除されます。False の場合、CDR レコードは無期限に保持されます。  <br/> |正  <br/> |
|KeepCallDetailForDays  <br/> |CDR レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。  <br/> KeepCallDetailForDays には、1 ～ 2,562 (約 7 年間の日数に相当) の範囲の任意の整数値を設定できます。  <br/> |60 (日)  <br/> |
|KeepErrorReportForDays  <br/> |CDR エラー報告が保持される日数を示します。指定した日数を超えるレポートは自動的に削除されます。 CDR エラー 報告は、Skype for Business Server などのクライアント アプリケーションによってアップロードされた診断レポートです。  <br/> このプロパティには、1 ～ 2,562 (日) の範囲の任意の整数値に指定できます。  <br/> |60 (日)  <br/> |
   
同様に、一部の QoE 設定の既定値を以下の表に示します。
  
|**プロパティ**|**説明**|**既定値**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |QoE 監視が有効かどうかを示します。True の場合、すべての QoE レコードが収集され、監視データベースに書き込まれます。  <br/> |正  <br/> |
|EnablePurging  <br/> |QoE レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepQoEDataForDays プロパティで指定されている期間を過ぎると、レコードが削除されます。False の場合、QoE レコードは無期限に保持されます。  <br/> |正  <br/> |
|KeepQoEDataForDays  <br/> |QoE レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。  <br/> KeepCallDetailForDays は、1 ～ 2562 (日) の範囲の任意の整数値に設定できます。  <br/> |60 日  <br/> |
   
これらのグローバル設定を変更する必要がある場合は、次のコマンドレットと Set-CsCdrConfiguration使用Set-CsQoEConfigurationできます。 たとえば、このコマンド (Skype for Business Server 管理シェル内から実行) は、CDR 監視をグローバル スコープで無効にします。これは、EnableCDR プロパティを False ($False) に設定することで行われます。
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

監視を無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されず、バックエンド監視データベースがアンインストールされたり、その他の影響がこのデータベースに及んだりすることもありません。 Skype for Business Server 管理シェルを使用して CDR または QoE の監視を無効にする場合は、Skype for Business Server による監視データの収集とアーカイブを一時的に停止する必要があります。 この場合、次のように EnableCDR プロパティの設定を True ($True) に戻すだけで、CDR データの収集とアーカイブを再開できます。
  
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

詳細については、Skype for Business Server 管理シェル内から次のコマンドを入力します。
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
