---
title: ビジネス サーバーの Skype の通話の詳細記録と品質のエクスペリエンスの設定を構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '概要: は、Skype のビジネス サーバーの CDR および QoE を構成する方法について説明します。'
ms.openlocfilehash: babc2ebe7901c19048624194b38e4cfa143e8f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894655"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>ビジネス サーバーの Skype の通話の詳細記録と品質のエクスペリエンスの設定を構成します。
 
**の概要:** Skype のビジネス サーバーの CDR および QoE を構成する方法について説明します。
  
CDR と QoE の Skype のビジネス サーバーの SQL Server レポート サービスのレポートを使用して監視を構成します。
  
## <a name="configure-cdr-and-qoe"></a>CDR および QoE の構成

監視ストアとフロント エンド プール、監視ストアを設定してから、インストールおよび構成されている SQL Server レポート サービス監視レポートに関連付けた後は、呼び出しの詳細記録 (CDR) とエクスペリエンスの品質 (QoE) を管理することSkype ビジネス サーバー管理シェルを使用して監視します。 Skype ビジネス サーバー管理シェル コマンドレットを使用すると、CDR と QoE の特定のサイト、または、全体の Skype ビジネス サーバーの配置のための監視を無効にするにはだけでこのコマンドを実行できます。
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

ビジネス サーバーの Skype をインストールするときは、CDR と QoE の両方のグローバル構成設定の定義済みコレクションもインストールされます。 以下の表に、通話詳細記録で比較的よく使用される一部の設定の既定値を示します。
  
|**プロパティ**|**説明**|**既定値**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |CDR が有効かどうかを示します。True の場合、すべての CDR レコードが収集され、監視データベースに書き込まれます。  <br/> |True  <br/> |
|EnablePurging  <br/> |CDR レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepCallDetailForDays プロパティ (CDR レコードの場合) および KeepErrorReportForDays プロパティ (CDR エラーの場合) で指定されている期間を過ぎると、レコードが削除されます。False の場合、CDR レコードは無期限に保持されます。  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |CDR レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。  <br/> KeepCallDetailForDays には、1 ～ 2,562 日 (約 7 年間) の間の整数値を設定できます。  <br/> |60 (日)  <br/> |
|KeepErrorReportForDays  <br/> |CDR エラー報告を保持する日数を示します。指定した日数より古いすべてのレポートが自動的に削除されます。 CDR エラー報告は、Skype ビジネス サーバーのクライアント アプリケーションによってアップロードされた診断のレポートです。  <br/> このプロパティには、1 ～ 2,562 (日) の範囲の任意の整数値に指定できます。  <br/> |60 (日)  <br/> |
   
同様に、一部の QoE 設定の既定値を以下の表に示します。
  
|**プロパティ**|**説明**|**既定値**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |QoE 監視が有効かどうかを示します。True の場合、すべての QoE レコードが収集され、監視データベースに書き込まれます。  <br/> |True  <br/> |
|EnablePurging  <br/> |QoE レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepQoEDataForDays プロパティで指定されている期間を過ぎると、レコードが削除されます。False の場合、QoE レコードは無期限に保持されます。  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |QoE レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。  <br/> KeepCallDetailForDays は、1 ～ 2,562 (日) の範囲の任意の整数値に設定できます。  <br/> |60 (日)  <br/> |
   
これらのグローバル設定を変更する必要がある場合これを行う一連の CsCdrConfiguration とセット CsQoEConfiguration コマンドレットを使用しています。 (内から実行、Skype ビジネス サーバー管理シェルの) 次のコマンドが CDR は、グローバル スコープで監視を無効にするなど、False ($False) に、EnableCDR プロパティを設定することによって行われます。
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

監視を無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されず、バックエンド監視データベースがアンインストールされたり、その他の影響がこのデータベースに及んだりすることもありません。 CDR または QoE の監視を無効にするのには Skype ビジネス サーバー管理シェルを使用すると、実際には、ビジネスのサーバーから収集し、監視データをアーカイブに Skype を一時的に停止です。 この場合、次のように EnableCDR プロパティの設定を True ($True) に戻すだけで、CDR データの収集とアーカイブを再開できます。
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

同様に、次のコマンドは、QoE レコードの削除をグローバル スコープで無効にします。
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

CDR と QoE の構成設定は、グローバル設定だけでなく、サイト スコープに割り当てることもできます。この操作を行うと、監視についての管理の柔軟性が向上します。たとえば、管理者は Redmond サイトで CDR 監視を有効にする一方で Dublin サイトでは CDR 監視を無効にできます。新しい CDR 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

サイト スコープで構成されたこの設定は、グローバル スコープで構成された設定よりも優先されることに注意してください。たとえば、CDR 監視がグローバル スコープで有効になっていても、サイト スコープ (Redmond サイト) では無効になっているとします。この場合、Redmond サイト内のユーザーについては通話詳細記録の情報がアーカイブされません。ただし、その他のサイト内のユーザー (つまり、Redmond サイトの設定ではなくグローバル設定によって管理されているユーザー) の通話詳細記録の情報はアーカイブされます。
  
新しい QoE 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

詳細については、サーバー管理シェルのビジネスから、Skype 内の次のコマンドを入力します。
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
