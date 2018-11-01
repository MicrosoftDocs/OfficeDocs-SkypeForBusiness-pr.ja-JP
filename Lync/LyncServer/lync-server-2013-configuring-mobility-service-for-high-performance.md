---
title: 高いパフォーマンスを実現する Mobility Service の構成
TOCTitle: 高いパフォーマンスを実現する Mobility Service の構成
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48273477
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 高いパフォーマンスを実現する Mobility Service の構成

 

_**トピックの最終更新日:** 2013-02-17_

インターネット インフォメーション サービス (IIS) 7.5 に Lync Server 2013 Mobility Service をインストールするとき、Mobility Service インストーラーにより、フロント エンド サーバーで一部のパフォーマンス設定が構成されます。モビリティでは IIS 7.5 を使用することをお勧めします。Windows Server 2008 で IIS 7.0 を使用する場合は、これらの設定を手動で構成する必要があります。これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。

パフォーマンス設定は、次のとおりです。

  - **maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。

  - **maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。

  - ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。

  - HTTP.sys のキューの制限は 1,000 に設定されます (既定)。

IIS 7.0 を使用する場合、マイクロソフト サポート技術情報の記事 2290617「修正プログラム: 修正 ASP.NET の一部のプロパティを各アプリケーション プールの IIS 7.0 の構成を有効にするのには」([http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x411)) から入手できる更新プログラムをインストールすることをお勧めします。これにより、Mobility Service に対してのみ変更を適用でき、他の Web サービスには影響を及ぼしません。

以下の手順では、サポート技術情報の記事 2290617 から入手できる更新プログラムをインストールしない場合に、IIS 7.0 で ASP.NET の同時要求とスレッドの最大値を変更する方法について説明します。ただし、サポート技術情報の記事 2290617 にある更新プログラムをインストールする場合でも、記事にあるドキュメントを使用して、Mobility の内部および外部 IIS アプリケーション プールに対してのみ同じ変更を適用する必要があります。この場合、ASP.NET 設定用に別の構成ファイルを使用します。


> [!IMPORTANT]
> 以下の手順を使用して最大値を変更する場合、変更はすべての IIS アプリケーション プールに影響します。



これらの設定を構成する方法の詳細については、「[http://go.microsoft.com/fwlink/?linkid=234537\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=234537%26clcid=0x411)」を参照してください。

## 同時要求とスレッドの最大数を変更するには

1.  \[**スタート**\] ボタンをクリックし、\[**ファイル名を指定して実行**\] をクリックします。

2.  \[**ファイル名を指定して実行**\] ボックスで、次のように入力します。
    
        notepad %SystemRoot%\Microsoft.NET\Framework64\v2.0.50727\Aspnet.config

3.  \[**OK**\] をクリックします。

4.  次の \<system.web\> 要素を、Aspnet.config ファイル内の \<configuration\> 要素の子として追加するか置換します。
    
        <system.web>
        <applicationPool maxConcurrentRequestsPerCPU="<#>" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>
        </system.web>
    
    このセクションで前述したように、\# は制限を解除する 0 か新しい数字です。

5.  Aspnet.config ファイルを保存し、メモ帳を閉じます。

