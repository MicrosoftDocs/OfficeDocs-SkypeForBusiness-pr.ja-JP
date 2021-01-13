---
title: Skype for Business クライアントでセットアップ のコマンド ライン オプションを使用する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: 新しいセットアップSetup.exeコマンド ライン操作の詳細Officeします。'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837207"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Skype for Business クライアントでセットアップ のコマンド ライン オプションを使用する
 
**概要:** このセットアップSetup.exeコマンド ライン操作についてOfficeします。
  
Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。 通常、セットアップのコマンド ライン オプションを使用する代わりに、製品のセットアップと機能のカスタマイズに Office カスタマイズ ツールと Config.xml ファイルを使用します。
  
Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。
  
**Office セットアップ コマンドライン オプション**

|**セットアップ コマンドライン オプション**|**説明**|
|:-----|:-----|
|/admin  <br/> |Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。  <br/> |
|/adminfile [パス]  <br/> |指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。  <br/> |
|/config [パス]  <br/> |インストール時にセットアップによって使用される Config.xml ファイルを指定します。 /config オプションを使用して、Skype for Business Config.xmlカスタマイズしたファイルを指定します。次に例を示します。  `/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |メンテナンス モードでセットアップを実行し、既存の Office インストールに変更を加えるために、変更された Config.xml ファイルと共に使用されます。 たとえば、/modify オプションを使用して Skype for Business の機能を追加または削除できます。  <br/> |
|/repair Skype  <br/> |ユーザーのコンピューターからセットアップを実行し、Skype for Business を修復します。  <br/> |
|/uninstall Skype  <br/> |セットアップを実行して、ユーザーのコンピューターから Skype for Business を削除します。  <br/> |
   


