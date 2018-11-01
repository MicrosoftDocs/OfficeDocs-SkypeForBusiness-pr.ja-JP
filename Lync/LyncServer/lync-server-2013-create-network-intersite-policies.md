---
title: Lync Server 2013 でのネットワーク サイト間ポリシーの作成
TOCTitle: Lync Server 2013 でのネットワーク サイト間ポリシーの作成
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48273291
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのネットワーク サイト間ポリシーの作成

 

_**トピックの最終更新日:** 2012-10-19_

*ネットワーク サイト間ポリシー*は、WAN リンクで直接接続されたサイト間の帯域幅制限を定義します。

詳細については、Lync Server 管理シェルのドキュメントに記載されている次のコマンドレットを参照してください。

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)


> [!IMPORTANT]
> ネットワーク サイト間ポリシーが必要なのは、2 つのネットワーク サイト間に直接クロス リンクがある場合<EM>のみ</EM>です。



North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。 この 2 つのサイトでは、適切な帯域幅ポリシー プロファイルを適用するサイト間ポリシーが必要です。 次の例は、20Mb\_Link プロファイルを適用します。

## ネットワーク サイト間ポリシーを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  New-CsNetworkInterSitePolicy コマンドレットを実行してネットワーク サイト間ポリシーを作成し、直接クロス リンクで接続された 2 つのサイトに対して適切な帯域幅ポリシー プロファイルを適用します。たとえば、以下を実行します。
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  必要に応じてステップ 2 を繰り返し、直接クロス リンクで接続されたすべてのネットワーク サイトのペアに対してネットワーク サイト間ポリシーを作成します。

