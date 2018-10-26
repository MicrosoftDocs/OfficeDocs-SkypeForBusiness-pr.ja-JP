---
title: ネットワーク サイトのリンクの構成
TOCTitle: ネットワーク サイトのリンクの構成
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48272656
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク サイトのリンクの構成

 

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) 構成内で、直接リンクされているサイト間の帯域幅の制限を定義するネットワーク サイト間ポリシーを作成できます。 ネットワーク サイトが直接リンクを共有している場合、その 2 つのサイト間の音声とビデオの接続に対する帯域幅の制限を定義できます。Lync Server コントロール パネルを使用してネットワーク サイト ポリシーを構成することはできません。ネットワーク サイト ポリシーは、Lync Server 管理シェルのコマンドレットによってのみ構成できます。Lync Server 管理シェルでは、ネットワーク サイト リンク (ネットワーク サイト間ポリシーとも呼ばれます) を作成、変更、および削除できます。

## ネットワーク サイト リンクを作成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド プロンプトで、使用している構成で有効な値に置き換えて、次のコマンドを入力します。
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    この例では、ネットワーク サイト Reno と Portland の間の帯域幅の制限を設定する、Reno\_Portland という名前の新しいネットワーク サイト リンクを作成します。 ネットワーク サイトと帯域幅ポリシーのプロファイルが、このコマンドを実行する前に既に存在している必要があります。

パラメーターの詳細な説明については、Lync Server 管理シェルのドキュメントの「[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)」を参照してください。 ネットワーク サイト リンクに適用できる帯域幅ポリシーのプロファイルの一覧を取得するには、**Get-CsNetworkBandwidthPolicyProfile** コマンドレットを呼び出します。詳細については、Lync Server 管理シェルのドキュメントの「[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)」を参照してください。

## ネットワーク サイト リンクを変更するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  特定のネットワーク サイト リンクのプロパティを変更するには、**Set-CsNetworkInterSitePolicy** コマンドレットを使用します。 接続されたサイトの一方 (または両方) を変更したり、リンクに関連付けられた帯域幅ポリシーのプロファイルを変更したりできます。 次に、Reno\_Portland という名前のサイト リンクの帯域幅ポリシーのプロファイルを変更する例を示します。
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

パラメーターの詳細な説明については、Lync Server 管理シェルのドキュメントの「[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)」を参照してください。

## ネットワーク サイト リンクを削除するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  ネットワーク サイト リンクを削除するには、**Remove-CsNetworkInterSitePolicy** コマンドレットを使用します。 次の例では、Reno\_Portland ネットワーク サイト リンクを削除します。
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

パラメーターの詳細な説明については、Lync Server 管理シェルのドキュメントの「[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)」を参照してください。

## 関連項目

#### 概念

[通話受付管理のコマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/)  

#### その他のリソース

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

