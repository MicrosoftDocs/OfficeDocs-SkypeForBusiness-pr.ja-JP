---
title: Skype for Business クライアントでセットアップコマンドラインオプションを使用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: Office のセットアップでの setup.exe コマンドラインの操作について説明します。'
ms.openlocfilehash: a84c1f8a69bdff07dfec5e274932a522bf139c9a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234837"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Skype for Business クライアントでセットアップコマンドラインオプションを使用する
 
**概要:** Office のセットアップでの setup.exe コマンドラインの操作について説明します。
  
Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。 通常、セットアップコマンドラインオプションを使う代わりに、Office カスタマイズツールと Config.xml ファイルを使用して、製品のセットアップと機能のカスタマイズを行います。
  
Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。
  
**Office セットアップ コマンドライン オプション**

|**セットアップ コマンドライン オプション**|**説明**|
|:-----|:-----|
|/admin  <br/> |Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。  <br/> |
|/adminfile [パス]  <br/> |指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。  <br/> |
|/config [パス]  <br/> |インストール時にセットアップで使用する Config.xml ファイルを指定します。 次の例のように、Skype for Business のインストール用にカスタマイズした Config.xml ファイルを指定するには、/config オプションを使用します。`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。 たとえば、/modify オプションを使用して、Skype for Business の機能を追加または削除することができます。  <br/> |
|/repair Skype  <br/> |ユーザーのコンピューターからセットアップを実行して、Skype for Business を修復します。  <br/> |
|/uninstall Skype  <br/> |セットアップを実行して、ユーザーのコンピューターから Skype for Business を削除します。  <br/> |
   


