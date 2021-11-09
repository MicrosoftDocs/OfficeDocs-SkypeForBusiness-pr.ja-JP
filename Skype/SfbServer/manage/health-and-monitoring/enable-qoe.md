---
title: '[エクスペリエンスの品質を有効にする] Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '概要: エクスペリエンスの品質 (QoE) を有効にする方法についてSkype for Business Server。'
ms.openlocfilehash: 89c6a41a356355ea5ac717a10e2848aa16d94249
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863574"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>[エクスペリエンスの品質を有効にする] Skype for Business Server

**概要: エクスペリエンス** の品質 (QoE) を有効にする方法についてSkype for Business Server。

QoE (Quality of Experience) は、メディアの品質と、通話およびセッションに関係する参加者、デバイス名、ドライバー、IP アドレス、およびエンドポイントの種類についての情報を示す数値データを記録します。詳細については、「計画」のドキュメントの「[Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)」を参照してください。

組織全体または組織内の各サイトで QoE を有効にするには、次の手順を実行します。

> [!NOTE]
> QoE を有効にするには、まず、監視を構成して、監視バック エンド データベースに接続する必要があります。詳細については、「[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)」を参照してください。

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して QoE をSkype for Business Serverするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4. [**QoE データ**] ページで、表から該当するコレクションをクリックして、[**操作**]、[**QoE を有効にする**] の順にクリックします。

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用して QoE をWindows PowerShellする

QoE を有効にするには、Windows PowerShell **Set-CsQoEConfiguration コマンドレットを使用** します。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。

### <a name="to-enable-qoe-for-a-single-location"></a>1 つの場所に対して QoE を有効にするには

 QoE を有効にするには、EnableQoE パラメーターを True ($True) に設定します。

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>1 つの場所に対して QoE を無効にするには

 QoE を無効にするには、EnableQoE パラメーターを False ($False) に設定します。これによって監視がアンインストールされることはありません。QoE データの収集と保存が停止されるだけです。

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>複数の場所の QoE を 1 つのコマンドで有効にするには

 このコマンドを実行すると、組織内で現在使用されているすべての QoE 構成設定に対して QoE が有効になります。

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

詳細については [、「Set-CsQoEConfiguration」を参照してください](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。

## <a name="see-also"></a>関連項目

[監視の計画](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[監視の展開](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)