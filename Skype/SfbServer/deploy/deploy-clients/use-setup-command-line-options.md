---
title: クライアントでセットアップ コマンド ライン オプションを使用Skype for Businessする
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: セットアップでのコマンド Setup.exe操作の詳細Officeします。'
ms.openlocfilehash: 6a64ac821019f49f8cbb4988ad0e42da0363245b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850486"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>クライアントでセットアップ コマンド ライン オプションを使用Skype for Businessする
 
**概要:** 詳細については、Setup.exeセットアップでのコマンド ライン操作Office説明します。
  
Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。 通常、セットアップ コマンド ライン オプションを使用する代わりに、Office カスタマイズ ツールと Config.xml ファイルを使用して製品のセットアップと機能のカスタマイズを行います。
  
Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。
  
**Office セットアップ コマンドライン オプション**

|**セットアップ コマンドライン オプション**|**説明**|
|:-----|:-----|
|/admin  <br/> |Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。  <br/> |
|/adminfile [パス]  <br/> |指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。  <br/> |
|/config [パス]  <br/> |インストール時にセットアップによって使用される Config.xml ファイルを指定します。 /config オプションを使用して、次Config.xmlインストール用にカスタマイズSkype for Businessファイルを指定します。`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |メンテナンス モードでセットアップを実行し、既存の Office インストールに変更を加えるために、変更された Config.xml ファイルと共に使用されます。 たとえば、/modify オプションを使用して、他の機能を追加またはSkype for Businessできます。  <br/> |
|/repair Skype  <br/> |ユーザーのコンピューターからセットアップを実行して、コンピューターを修復Skype for Business。  <br/> |
|/uninstall Skype  <br/> |セットアップを実行して、Skype for Businessコンピューターからファイルを削除します。  <br/> |
   


