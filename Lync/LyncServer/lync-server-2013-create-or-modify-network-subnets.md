---
title: ネットワーク サブネットの作成または変更
TOCTitle: ネットワーク サブネットの作成または変更
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48271426
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク サブネットの作成または変更

 

_**トピックの最終更新日:** 2013-02-21_

ネットワーク サブネットは、そのサブネットに所属するホストの地理的な場所を指定するために、ネットワーク サイトに関連付ける必要があります。Lync Server コントロール パネルを使用するとサブネットを構成できます。Lync Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。ネットワーク サブネットの削除の詳細については、「[ネットワーク サブネットの削除](lync-server-2013-deleting-network-subnets.md)」を参照してください。

通話受付管理 (CAC) を実装している大部分の Microsoft Lync Server 2013 の展開には、一般的に、多くのサブネットが存在します。このため、Lync Server 管理シェルからサブネットを構成するのが、多くの場合、最も良い方法です。Lync Server 管理シェルから、Windows PowerShell のコマンドレット **Import-CSV** とともに **New-CsNetworkSubnet** を呼び出すことができます。これらのコマンドレットを同時に使用することで、csv (コンマ区切り値) ファイルからサブネット設定を読み取って、同時に複数のサブネットを作成できます。csv ファイルからサブネットを作成する方法の例については、「[New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。

## ネットワーク サブネットを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**サブネット**\] をクリックします。

4.  \[**サブネット**\] ページで、\[**新規**\] をクリックします。

5.  \[**新しいサブネット**\] で、\[**サブネット ID**\] フィールドに値を入力します。 これは、IP アドレス (174.11.12.0 など) である必要があります。また、サブネットで定義される IP アドレス範囲の最初のアドレスである必要があります。

6.  \[**マスク**\] フィールドで、1 ～ 32 の数値を入力します。
    
    > [!NOTE]
    > この値は、作成するサブネットに適用するビットマスクです。


7.  \[**ネットワーク サイト ID**\] で、このサブネットが所属するサイトを選択します。

8.  (オプション) \[**説明**\] フィールドに値を入力して、名前だけでは表現することのできないこのサブネットの詳細情報を提供します。

9.  \[**確定**\] をクリックします。

## ネットワーク サブネットを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**サブネット**\] をクリックします。

4.  \[**サブネット**\] ページで、変更するサブネットをクリックします。

5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

6.  \[**サブネットの編集**\] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。 ビットマスクを変更する場合は、変更後もサブネット ID がサブネットで定義される IP アドレス範囲の最初のアドレスでなければならないことに注意してください。

7.  \[**確定**\] をクリックします。

## 関連項目

#### タスク

[ネットワーク サブネットの削除](lync-server-2013-deleting-network-subnets.md)  

#### 概念

[Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成](lync-server-2013-about-network-regions-sites-and-subnets.md)  

#### その他のリソース

[New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet)

