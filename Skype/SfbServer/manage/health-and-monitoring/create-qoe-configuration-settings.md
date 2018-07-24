---
title: ビジネス サーバーのため、Skype で高品質なエクスペリエンスの構成設定を作成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '概要: は、Skype でビジネス サーバー用のエクスペリエンスの品質 (QoE) の設定について説明します。'
ms.openlocfilehash: 678f57ba06008244bf9872ee44b26ea0c1e9a0f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968196"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>ビジネス サーバーのため、Skype で高品質なエクスペリエンスの構成設定を作成します。
 
**の概要:** ビジネス サーバーの Skype の高品質のエクスペリエンス (QoE) の設定について説明します。
  
Quality of Experience (QoE) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。
  
ビジネス サーバー、1 つの Skype をインストールすると QoE 構成設定のグローバル コレクションが作成されます。 管理者は、サイト スコープでカスタム設定を作成することもできます。 これらのサイト スコープの設定は、グローバル設定に優先して使用されます。 たとえば、Redmond サイト用のサイト スコープの設定を作成した場合は、グローバル設定ではなくこれらの設定を使用して Redmond の QoE が管理されます。
  
QoE 構成設定は、ビジネス サーバーのコントロール パネルまたは[新規 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)コマンドレットのいずれかの Skype を使用して作成できます。 新しい設定を作成するビジネス サーバーのコントロール パネルの Skype を使用している場合に使用可能な次のオプションになります。
  
|**UI 設定**|**PowerShell パラメーター**|**説明**|
|:-----|:-----|:-----|
|名前  <br/> |Identity  <br/> |作成される設定の一意の ID。QoE 構成設定は、サイト スコープでのみ作成できます。  <br/> |
|[QoE データの監視を有効にする]  <br/> |EnableQoE  <br/> |QoE レコードを収集して、監視データベースに保存するかどうかを指定します。  <br/> |
|[QoE データの消去を有効にする]  <br/> |EnablePurging  <br/> |[**QoE データの最大保持期間 (日)**] プロパティに定義された期間が経過した後、レコードを削除するかどうかを指定します。 <br/> |
|[QoE データの最大保存期間 (日)]  <br/> |KeepQoEDataForDays  <br/> |データベースから削除するまで QoE データを保存する日数。削除が無効の場合、この値は無視されます。  <br/> |
   
> [!NOTE]
> 新規 CsQoEConfiguration コマンドレットには、ビジネス サーバーのコントロール パネルの Skype では利用できない追加のオプションが含まれています。 詳細については、[新規 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)のヘルプ トピックを参照してください。
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、QoE 構成設定を作成するには

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator のロールのメンバーとしてコンピューターにログオンします。 詳細については、**セットアップのアクセス許可の委任**を参照してください。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。
    
4. [**QoE データ**] ページで、[**新規**] をクリックします。
    
5. [**サイトの選択**] でポリシーを適用するサイトをクリックし、[**OK**] をクリックします。
    
6. [**新しい QoE の設定**] で、次の手順を実行します。
    
   - [**QoE データの監視を有効にする**] を選択して、監視を有効にします。
    
   - [**QoE データの削除を有効にする**] を選択して、削除を有効にします。
    
   - [**QoE の最大保持期間 (日)**] で、QoE レコードを保持する最大日数を選択します。
    
7. [**コミット**] をクリックします。
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、QoE 構成設定を作成します。

QoE 構成設定を作成するには、Windows PowerShell と新規 CsQoEConfiguration コマンドレットを使用します。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>QoE 構成設定の新しいコレクションを作成するには

 次のコマンドは、Redmond サイトに適用される QoE 構成設定の新しいコレクションを作成します。
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 監視が無効になっている QoE 構成設定の新しいコレクションを作成するには

 必須である Identity パラメーターを除いて、先行するコマンドでパラメーターが指定されないため、構成設定の新しいコレクションでは、すべてのプロパティで既定値が使用されます。別のプロパティ値を使用する設定を作成するには、単に適切なパラメーターとパラメーター値を指定します。たとえば、Quality of Experience (QoE) レコードを既定で無効にする QoE 構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>QoE 構成設定の新しいコレクションを作成するときに複数のプロパティ値を指定するには

 複数のパラメーターを含めることで、複数のプロパティ値を指定できます。たとえば、次のコマンドは、QoE データを 30 日間保持し、以前のデータを午前 3 時に削除する新しい設定を構成します。
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

詳細については、[新規 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

