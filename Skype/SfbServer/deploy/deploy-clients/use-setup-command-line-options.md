---
title: Skype でビジネスのクライアントのセットアップ コマンド ライン オプションを使用してください。
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: は、Office のセットアップで、Setup.exe コマンドライン操作について説明します。'
ms.openlocfilehash: d3bf2b4d867fbbb43c346f2b9572de329ec66bdc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880279"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Skype でビジネスのクライアントのセットアップ コマンド ライン オプションを使用してください。
 
**の概要:** Office セットアップで、Setup.exe コマンドライン操作について説明します。
  
Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。 セットアップのコマンド ライン オプションを使用するのではなく通常を使用します、Office カスタマイズ ツールと Config.xml ファイルの製品のセットアップおよび機能のカスタマイズ。
  
Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。
  
**Office セットアップ コマンドライン オプション**

|**セットアップ コマンドライン オプション**|**説明**|
|:-----|:-----|
|/admin  <br/> |Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。  <br/> |
|/adminfile [パス]  <br/> |指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。  <br/> |
|/config [パス]  <br/> |インストール時にセットアップで使用する Config.xml ファイルを指定します。 /Config オプションを使用して、カスタマイズした Skype のビジネス インストールの場合、たとえば Config.xml ファイルを指定します。`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。 たとえば、使用することができます、またはビジネス機能の Skype を削除または追加するオプションを変更します。  <br/> |
|/repair Skype  <br/> |ビジネス用の Skype を修復するユーザーのコンピューターからセットアップを実行します。  <br/> |
|/uninstall Skype  <br/> |ユーザーのコンピューターからビジネス用の Skype を削除するのにはセットアップを実行します。  <br/> |
   


