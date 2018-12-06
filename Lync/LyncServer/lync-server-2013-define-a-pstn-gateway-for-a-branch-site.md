---
title: 'Lync Server 2013: ブランチ サイト用の PSTN ゲートウェイの定義'
TOCTitle: ブランチ サイト用の PSTN ゲートウェイの定義
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48272790
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのブランチ サイト用の PSTN ゲートウェイの定義

 

_**トピックの最終更新日:** 2012-09-21_

少なくとも 1 つの フロント エンド プールまたは Standard Edition サーバーを含む中央サイトでこの手順を実行します。


> [!IMPORTANT]
> 手順を実行する前に、以下の条件が整っている必要があります。 
> <UL>
> <LI>
> <P>Lync Server 2013&nbsp; 通信ソフトウェアが中央サイトで設定されている必要があります。</P>
> <LI>
> <P>仲介サーバーが中央サイトに展開されている必要があります。</P></LI></UL>



## PSTN ゲートウェイを定義するには

1.  \[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。

2.  コンソール ツリーで中央サイトを展開して、\[**ブランチ オフィス サイト**\] を展開し、公衆交換電話網 (PSTN) ゲートウェイを定義するブランチ サイトの名前を展開し、次に \[**共有コンポーネント**\] を展開します。

3.  \[**PSTN ゲートウェイ**\] を右クリックし、\[**新しい IP/PSTN ゲートウェイ**\] をクリックします。

4.  \[**新しい IP/PSTN ゲートウェイの定義**\] ダイアログ ボックスで、\[**ゲートウェイ FQDN または IP アドレス**\] をクリックして、ブランチ サイトに展開するゲートウェイの完全修飾ドメイン名 (FQDN) または IP アドレスを入力します。

5.  \[**IP/PSTN ゲートウェイのリッスン ポート**\] をクリックして、既定値をそのまま使用します。

6.  \[**SIP トランスポート プロトコル**\] リストで、ゲートウェイで使用するトランスポート プロトコルをクリックして、\[**OK**\] をクリックします。
    
    > [!NOTE]
    > セキュリティ上の理由のため、トランスポート層セキュリティ (TLS) をサポートする PSTN ゲートウェイの使用を強くお勧めします。



> [!TIP]
> コマンドレット <STRONG>Set-CsPstnGateway</STRONG> を使用して、PSTN ゲートウェイのプロパティを変更します。詳細については、Lync Server 管理シェルのヘルプの「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>」を参照してください。



ブランチ サイトの復元の **次のステップ**: [Lync Server 2013 でブランチ サイト復元を実現するためのユーザーの構成](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

## 関連項目

#### 概念

[Lync Server 2013 の PSTN ゲートウェイの展開オプション](lync-server-2013-pstn-gateway-deployment-options.md)

