---
title: 'Lync Server 2013: VDI の使用環境の準備'
TOCTitle: VDI の使用環境の準備
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48273164
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VDI の Lync Server 2013 使用環境の準備

 

_**トピックの最終更新日:** 2013-02-22_

Lync VDI プラグインを使用する環境を準備するには、次の手順を実行する必要があります。

1.  Lync Server 2013 で、すべての VDI ユーザーに対して EnableMediaRedirection が TRUE に設定されていることを確認します。詳細については、[New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) コマンドレットおよび [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) コマンドレットに関するヘルプ トピックを参照してください。

2.  データ センター コンピューターで、 Lync 2013 クライアントをすべての仮想マシンにインストールします。

3.  ローカル コンピューターで、 Lync VDI プラグインをインストールします。

