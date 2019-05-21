---
title: Skype for Business Server のエクスペリエンスの品質を有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '概要: Skype for Business Server の Quality of Experience (QoE) を有効にする方法について説明します。'
ms.openlocfilehash: 90110c5664e80ac1d4f9d382c20e0fd58d9ce134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305711"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Skype for Business Server のエクスペリエンスの品質を有効にする

**概要:** Skype For business Server の Quality of Experience (qoe) を有効にする方法について説明します。

QoE (Quality of Experience) は、メディアの品質と、通話およびセッションに関係する参加者、デバイス名、ドライバー、IP アドレス、およびエンドポイントの種類についての情報を示す数値データを記録します。詳細については、「計画」のドキュメントの「[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)」を参照してください。

組織全体または組織内の各サイトで QoE を有効にするには、次の手順を実行します。

> [!NOTE]
> QoE を有効にするには、まず、監視を構成して、監視バック エンド データベースに接続する必要があります。詳細については、「[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)」を参照してください。

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して QoE を有効にするには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4. [**QoE データ**] ページで、表から該当するコレクションをクリックして、[**アクション**]、[**QoE を有効にする**] の順にクリックします。

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して QoE を有効にする

QoE を有効にするには、Windows PowerShell と**Set-CsQoEConfiguration**指定コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。

### <a name="to-enable-qoe-for-a-single-location"></a>1 つの場所に対して QoE を有効にするには

 QoE を有効にするには、EnableQoE パラメーターを True ($True) に設定します。

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>1 つの場所に対して QoE を無効にするには

 QoE を無効にするには、EnableQoE パラメーターを False ($False) に設定します。これによって監視がアンインストールされることはありません。QoE データの収集と保存が停止されるだけです。

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>複数の場所の QoE を 1 つのコマンドで有効にするには

 このコマンドを実行すると、組織内で現在使用されているすべての QoE 構成設定に対して QoE が有効になります。

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

詳細については、「 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)」を参照してください。

## <a name="see-also"></a>関連項目

[モニタリングの計画](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

