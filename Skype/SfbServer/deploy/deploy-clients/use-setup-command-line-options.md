---
title: Skype for Business Server 2015 でセットアップ コマンド ライン オプションを使用する
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: は、Office のセットアップで、Setup.exe コマンドライン操作について説明します。'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でセットアップ コマンド ライン オプションを使用する
 
**の概要:**Office セットアップで、Setup.exe コマンドライン操作について説明します。
  
Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。 セットアップのコマンド ライン オプションを使用するのではなく通常を使用します、Office カスタマイズ ツールと Config.xml ファイルの製品のセットアップおよび機能のカスタマイズ。
  
Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。
  
**Office セットアップのコマンド ライン オプション**

|**セットアップ コマンド ライン オプション**|**説明**|
|:-----|:-----|
|/admin  <br/> |Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。  <br/> |
|/adminfile [パス]  <br/> |指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。  <br/> |
|/config [パス]  <br/> |インストール時にセットアップで使用する Config.xml ファイルを指定します。 /Config オプションを使用して、カスタマイズした Skype のビジネス インストールの場合、たとえば Config.xml ファイルを指定します。`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。 たとえば、使用することができます、またはビジネス機能の Skype を削除または追加するオプションを変更します。  <br/> |
|/repair Skype  <br/> |ビジネス用の Skype を修復するユーザーのコンピューターからセットアップを実行します。  <br/> |
|/uninstall Skype  <br/> |ユーザーのコンピューターからビジネス用の Skype を削除するのにはセットアップを実行します。  <br/> |
   
セットアップ コマンド ライン オプションの使用に関する詳細についてを参照してください[https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515)。 
  

