---
title: Skype for Business Server のエクスペリエンスの構成設定の品質設定を作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '概要: Skype for Business Server の Quality of Experience (QoE) 設定について説明します。'
ms.openlocfilehash: 5366937f1faa01e6533b51677122713ee9e839fa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818037"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server のエクスペリエンスの構成設定の品質設定を作成する
 
**概要:** Skype for Business Server の Quality of Experience (QoE) 設定について説明します。
  
Quality of Experience (QoE) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。
  
Skype for Business Server をインストールすると、QoE 構成設定のグローバルコレクションが1つ作成されます。 管理者は、サイト スコープでカスタム設定を作成することもできます。 これらのサイト スコープの設定は、グローバル設定に優先して使用されます。 たとえば、Redmond サイト用のサイト スコープの設定を作成した場合は、グローバル設定ではなくこれらの設定を使用して Redmond の QoE が管理されます。
  
QoE 構成設定を作成するには、Skype for Business Server コントロールパネルまたは[新しい-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)コマンドレットを使用します。 Skype for Business Server コントロールパネルを使用して新しい設定を作成する場合は、次のオプションを使用できます。
  
|**UI 設定**|**PowerShell パラメーター**|**説明**|
|:-----|:-----|:-----|
|名前  <br/> |Identity  <br/> |作成される設定の一意の ID。QoE 構成設定は、サイト スコープでのみ作成できます。  <br/> |
|[QoE データの監視を有効にする]  <br/> |EnableQoE  <br/> |QoE レコードを収集して、監視データベースに保存するかどうかを指定します。  <br/> |
|[QoE データの消去を有効にする]  <br/> |EnablePurging  <br/> |[**QoE データの最大保持期間 (日)**] プロパティに定義された期間が経過した後、レコードを削除するかどうかを指定します。 <br/> |
|[QoE データの最大保存期間 (日)]  <br/> |KeepQoEDataForDays  <br/> |データベースから削除するまで QoE データを保存する日数。削除が無効の場合、この値は無視されます。  <br/> |
   
> [!NOTE]
> 新しい-CsQoEConfiguration 設定コマンドレットには、Skype for Business Server コントロールパネルで利用できないその他のオプションが含まれています。 詳細については、「[新しい-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)方法」を参照してください。
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して QoE 構成設定を作成するには

1. RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。
    
4. [**QoE データ**] ページで、[**新規**] をクリックします。
    
5. [**サイトの選択**] でポリシーを適用するサイトをクリックし、[**OK**] をクリックします。
    
6. [**新しい QoE の設定**] で、次の手順を実行します。
    
   - [**QoE データの監視を有効にする**] を選択して、監視を有効にします。
    
   - [**QoE データの削除を有効にする**] を選択して、削除を有効にします。
    
   - [**QoE の最大保持期間 (日)**] で、QoE レコードを保持する最大日数を選択します。
    
7. [**コミット**] をクリックします。
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して QoE 構成設定を作成する

QoE 構成設定を作成するには、Windows PowerShell と、新しい-CsQoEConfiguration コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>QoE 構成設定の新しいコレクションを作成するには

 次のコマンドは、Redmond サイトに適用される QoE 構成設定の新しいコレクションを作成します。
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 監視が無効になっている QoE 構成設定の新しいコレクションを作成するには

 必須である Identity パラメーターを除いて、先行するコマンドでパラメーターが指定されないため、構成設定の新しいコレクションでは、すべてのプロパティで既定値が使用されます。別のプロパティ値を使用する設定を作成するには、単に適切なパラメーターとパラメーター値を指定します。たとえば、Quality of Experience (QoE) レコードを既定で無効にする QoE 構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>QoE 構成設定の新しいコレクションを作成するときに複数のプロパティ値を指定するには

 複数のパラメーターを含めることで、複数のプロパティ値を指定できます。たとえば、次のコマンドは、QoE データを 30 日間保持し、以前のデータを午前 3 時に削除する新しい設定を構成します。
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

詳細については、「[新しい-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)コマンドレット」のヘルプトピックを参照してください。
  

