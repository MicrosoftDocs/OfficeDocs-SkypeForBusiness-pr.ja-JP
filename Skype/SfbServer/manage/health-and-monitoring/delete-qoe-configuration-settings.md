---
title: '[エクスペリエンスの品質] 構成設定を削除Skype for Business Server'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '概要: エクスペリエンスの品質 (QoE) 設定を削除する方法については、Skype for Business Server。'
---

# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>[エクスペリエンスの品質] 構成設定を削除Skype for Business Server
 
**概要:** このページで、QoE (Quality of Experience) 設定を削除するSkype for Business Server。
  
QoE (Quality of Experience) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。
  
サーバーをインストールSkype for Business Server、QoE 構成設定の単一のグローバル コレクションが作成されます。 また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。 設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 サイト スコープの設定を削除すると、サイトの QoE はグローバル設定を使って管理されます。
  
グローバル設定を "削除" することもできます。 ただし、グローバル設定は実際に削除されるわけではありません。 代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。 たとえば、QoE 構成設定のコレクションでは削除が既定で有効になっています。 仮にグローバル コレクションを変更して削除を無効にしたとします。 後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。 この場合、削除が再び有効になることを意味します。
  
QoE 構成設定は、Skype for Business Serverコントロール パネルを使用するか、[Remove-CsQoEConfiguration コマンドレットを使用して削除](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)できます。
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して QoE 構成設定Skype for Business Server削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。
    
4. [**QoE データ**] ページで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
5. [**OK**] をクリックします。
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した QoE 構成設定の削除Windows PowerShellする

QoE 構成設定を削除するには、Windows PowerShell **Remove-CsQoEConfiguration コマンドレットを使用** します。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してリモート Windows PowerShell接続する方法Skype for Business Server [Microsoft Lync リモート PowerShell 管理」を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>指定した QoE 構成設定のコレクションを削除するには

 このコマンドは、Redmond サイトに適用された QoE 構成設定を削除します。
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>サイト スコープに適用されたすべての QoE 構成設定を削除するには

 このコマンドは、サイト スコープに適用されたすべての QoE 構成設定を削除します。
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 監視が無効にされたすべての QoE 構成設定を削除するには

 このコマンドは、QoE 監視が無効にされたすべての QoE 構成設定を削除します。
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

詳細については、「 [Remove-CsQoEConfiguration」を参照してください](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。
  
## <a name="see-also"></a>関連項目

[通話の詳細記録と Quality of Experience データベースを手動で削除Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)