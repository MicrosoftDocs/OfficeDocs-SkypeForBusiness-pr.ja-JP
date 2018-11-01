---
title: 'Lync Server 2013: Lync Server のハイブリッド環境の概要'
TOCTitle: Lync Server 2013 のハイブリッド環境の概要
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48271245
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のハイブリッド環境の概要

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 ハイブリッド環境とは、社内の Lync Server 2013 に属するユーザーと Lync Online に属するユーザーが混在し、それらのユーザーが、user@contoso.com など、同じドメインを共有している展開を表します。

## このガイドについて

このガイドでは、Lync Online と相互運用できるように Lync Server 2013 環境を構成するために必要なタスクと、Lync Online を使用するように社内の展開からユーザーを移動するために必要なタスクについて説明します。

## 必要条件

展開をハイブリッド環境用として構成するタスクを完了するためには、以下のアプリケーションとユーティリティがインストールされている必要があります。これらのファイルのインストーラーは、使用する展開用に提供されたインストール メディアに含まれています。また、以下のリストに示すリンクからも入手できます。

  - [Active Directory Federation Services 2.0 RTW - 日本語](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft Directory Synchronization Tool 9.1 (Microsoft Directory Synchronization Tool 9.1)](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [AD FS によるシングル サインオンに必要な Windows PowerShell をインストールする](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services サインイン アシスタント (msoidcli-7.0.msi) は Office 365 のデスクトップ セットアップに含まれており、Office 365 管理用ポータルからリンクされているダウンロード ページで入手できます。

## 管理者の資格情報

管理者の資格情報の入力を求められたときは、Office 365 テナントの管理者アカウントとして提供されたユーザー名とパスワードを使用します。この資格情報は、Active Directory フェデレーション サービス (AD FS) 2.0、ディレクトリ同期、シングル サインオン、およびフェデレーションを構成する場合や、Lync Online にユーザーを移行する場合にも使用します。

## Lync Online PowerShell への接続

管理者は、Windows PowerShell を使用して、Lync Online および Lync Online ユーザー アカウントを管理できるようになりました。そのためには、最初に Lync Online Connector モジュールを Microsoft ダウンロード センター (http://go.microsoft.com/fwlink/?LinkId=294688) からダウンロードしてインストールする必要があります。 Lync Online Connector モジュールのダウンロード、インストール、および使用方法の詳細について、および Windows PowerShell を使用して Lync Online を管理する方法の詳細については、「[Windows PowerShell による Lync Online の管理](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。

