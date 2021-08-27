---
title: '[エクスペリエンスの品質] 構成設定を作成Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '概要: エクスペリエンスの品質 (QoE) の設定について、Skype for Business Server。'
ms.openlocfilehash: 564ab88b349b578cf577893e4119e5e1ebf26fb1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585101"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>[エクスペリエンスの品質] 構成設定を作成Skype for Business Server
 
**概要:** エクスペリエンスの品質 (QoE) 設定の詳細については、Skype for Business Server。
  
QoE (Quality of Experience) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。
  
サーバーをインストールSkype for Business Server、QoE 構成設定の単一のグローバル コレクションが作成されます。 管理者は、サイト スコープでカスタム設定を作成することもできます。 これらのサイト スコープの設定は、グローバル設定に優先して使用されます。 たとえば、Redmond サイト用のサイト スコープの設定を作成した場合は、グローバル設定ではなくこれらの設定を使用して Redmond の QoE が管理されます。
  
QoE 構成設定は、コントロール パネルまたは[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)コマンドレットSkype for Business Server使用して作成できます。 コントロール パネルを使用Skype for Business Server新しい設定を作成する場合は、次のオプションを使用できます。
  
|**UI 設定**|**PowerShell パラメーター**|**説明**|
|:-----|:-----|:-----|
|名前  <br/> |ID  <br/> |作成される設定の一意の ID。QoE 構成設定は、サイト スコープでのみ作成できます。  <br/> |
|QoE データの監視を有効にする  <br/> |EnableQoE  <br/> |QoE レコードを収集し、監視データベースに保存するかどうかを指定します。  <br/> |
|QoE データの消去を有効にする  <br/> |EnablePurging  <br/> |[**QoE データの最大保持期間 (日)**] プロパティに定義された期間が経過した後、レコードを削除するかどうかを指定します。 <br/> |
|QoE データの最大保存期間 (日)  <br/> |KeepQoEDataForDays  <br/> |データベースから削除するまで QoE データを保存する日数。削除が無効の場合、この値は無視されます。  <br/> |
   
> [!NOTE]
> このNew-CsQoEConfigurationには、コントロール パネルで使用できないSkype for Business Serverが含まれています。 詳細については [、「New-CsQoEConfiguration」のヘルプ トピックを](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 参照してください。
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して QoE 構成設定をSkype for Business Serverするには

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。
    
4. [**QoE データ**] ページで、[**新規**] をクリックします。
    
5. [**サイトの選択**] でポリシーを適用するサイトをクリックし、[**OK**] をクリックします。
    
6. [**新しい QoE の設定**] で、次の手順を実行します。
    
   - [**QoE データの監視を有効にする**] を選択して、監視を有効にします。
    
   - [**QoE データの削除を有効にする**] を選択して、削除を有効にします。
    
   - [**QoE の最大保持期間 (日)**] で、QoE レコードを保持する最大日数を選択します。
    
7. [**確定**] をクリックします。
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用設定 QoE 構成Windows PowerShell作成する

QoE 構成設定を作成するには、Windows PowerShellコマンドレットをNew-CsQoEConfigurationします。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した[Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>QoE 構成設定の新しいコレクションを作成するには

 次のコマンドは、Redmond サイトに適用される QoE 構成設定の新しいコレクションを作成します。
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 監視が無効になっている QoE 構成設定の新しいコレクションを作成するには

 必須である Identity パラメーターを除いて、先行するコマンドでパラメーターが指定されないため、構成設定の新しいコレクションでは、すべてのプロパティで既定値が使用されます。別のプロパティ値を使用する設定を作成するには、単に適切なパラメーターとパラメーター値を指定します。たとえば、QoE レコードを既定で無効にする Quality of Experience 構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>QoE 構成設定の新しいコレクションを作成するときに複数のプロパティ値を指定するには

 複数のパラメーターを含めることで、複数のプロパティ値を指定できます。たとえば、次のコマンドは、QoE データを 30 日間保持し、古いデータを午前 3 時に削除する新しい設定を構成します。
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

詳細については [、New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
