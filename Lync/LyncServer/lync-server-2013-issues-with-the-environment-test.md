---
title: 環境テストに関する問題
TOCTitle: 環境テストに関する問題
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48274169
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 環境テストに関する問題

 

_**トピックの最終更新日:** 2012-09-21_

ベスト プラクティス アナライザーでは、Lync Server 2013 の環境がサポートされている構成であることを確認する方法を提供します。Active Directory Domain サービスのチェックの一環として、ベスト プラクティス アナライザーは次を行います。

  - Active Directory Domain サービスのフォレストとスキーマの準備を検証します。

  - 展開の Active Directory Domain サービスのサイトとドメインの数を特定します。

  - フォレストとドメインのレベルを確認します。

  - ドメイン コントローラーのバージョンを確認します。

  - ドメイン、構成、およびスキーマの名前付けコンテキストを特定します。

  - 有効なユーザーの数を特定します。

  - グローバル Active Directory Domain サービス設定が保存されている場所を確認します。

  - Lync Server のサービス接続ポイント (SCP) を確認します。

  - データベース バージョンを特定します。

## 環境での問題の解決

使用している環境に問題があることが環境テストで判明した場合、それらの問題は恐らく Active Directory の構成または特定のサーバーで実行されているソフトウェアのレベルの問題に起因します。たとえば、ベスト プラクティス アナライザーが Windows Server 2000 を実行しているドメイン コントローラーを環境で特定した場合、警告を発するため、Windows Server のサポート対象バージョンにドメイン コントローラーをアップグレードする必要があります。

