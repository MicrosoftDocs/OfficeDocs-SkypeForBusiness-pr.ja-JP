---
title: 'Lync Server 2013: 会議のための場所に基づくルーティングの構成'
TOCTitle: 会議のための場所に基づくルーティングの構成
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56270146
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での会議のための場所に基づくルーティングの構成

 

_**トピックの最終更新日:** 2016-12-08_

Location-Based Routing Conferencing アプリケーションは、Lync Server 2013 Location-Based Routing の構成に依存しています。主な構成は次のとおりです。

  - 会議の参加者の場所は、ネットワーク サイトに基づいて決定されます。場所に基づくルーティングを強制するには、ネットワーク サイトとその関連ネットワーク サブネットが Lync Server に定義されている必要があります。

  - 会議の場所に基づくルーティングを強制するため、Lync 参加者は場所に基づくルーティングを有効にしている必要があります。

  - 会議に参加する PSTN エンドポイントの場所に基づくルーティングを強制するには、PSTN エンドポイントとの接続に使用される SIP トランクが場所に基づくルーティング向けに構成されている必要があります。

Lync Server 2013 の場所に基づくルーティングの展開と構成の詳細については、「[場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)」を参照してください。

## Location-Based Routing Conferencing アプリケーションを有効にする

Location-Based Routing Conferencing アプリケーションは既定で無効になっています。このアプリケーションを有効にする前に、このアプリケーションに割り当てるのに適した優先順位を決める必要があります。この優先順位を決めるには、Lync Server 管理シェル で次のコマンドレットを実行します。

Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>

このコマンドレットで、\<Pool FQDN\> は Location-Based Routing Conferencing アプリケーションを有効にするプールです。

このコマンドレットは、Lync Server によってホストされるアプリケーションとそれぞれの優先順位の値の一覧を返します。Location-Based Routing Conferencing アプリケーションに割り当てられる優先順位の値は、「UdcAgent」アプリケーションより大きく、「DefaultRouting」、「ExumRouting」、「OutboundRouting」の各アプリケーションより小さいことが必要です。Location-Based Routing Conferencing アプリケーションには、「UdcAgent」アプリケーションより 1 ポイント高い優先順位の値を割り当てることをお勧めします。

たとえば、「UdcAgent」アプリケーションの優先順位の値が「2」、「DefaultRouting」アプリケーションの優先順位の値が「8」、「ExumRouting」アプリケーションの優先順位の値が「9」、「OutboundRouting」アプリケーションの優先順位の値が「10」の場合、Location-Based Routing Conferencing アプリケーションには優先順位の値として「3」を割り当てます。これにより、各アプリケーションの優先順位は次のような順序になります。他のアプリケーション (優先順位: 0 ～ 1)、「UdcAgent」(優先順位: 2)、Location-Based Routing Conferencing アプリケーション (優先順位: 3)、他のアプリケーション (優先順位: 4 ～ 8)、「DefaultRouting」(優先順位: 9)「ExumRouting」(優先順位: 10)、および「OutboundRouting」(優先順位: 11)。

Location-Based Routing Conferencing アプリケーションに適した優先順位の値が見つかったら、場所に基づくルーティングを有効にしているユーザーが属する各フロント エンド プール サーバー、または Standard Edition サーバーに次のコマンドレットを入力します。

New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

次に例を示します。

New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

このコマンドレットを使用したら、Location-Based Routing Conferencing アプリケーションが有効になっている、該当するプールのフロント エンド サーバー、または Standard Edition サーバーを再起動します。


> [!IMPORTANT]
> 場所に基づくルーティングの会議または取次転送への強制は、該当するプールのフロント エンド サーバー、または Standard Edition サーバーが再起動されるまで反映されません。上記のコマンドレットで <STRONG>–Critical</STRONG> を <STRONG>$true</STRONG> に設定した場合、Lync サービスはただちに再開されます。これらのサービスがすぐには再開されないようにするには、<STRONG>–Critical</STRONG> を当面 <STRONG>$false</STRONG> に設定し、後でサービスを再開したときに <STRONG>Set-CsServerApplication</STRONG> を使用して <STRONG>-Critical</STRONG> を <STRONG>$true</STRONG> に設定します。



Location-Based Routing Conferencing アプリケーションが正常に有効になり、該当するすべての Lync サーバーが再起動されると、場所に基づくルーティングを有効にしている Lync ユーザーによって開催されたすべての会議が監視され、PSTN 料が適切に課金されます。

