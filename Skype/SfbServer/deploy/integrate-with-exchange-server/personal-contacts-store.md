---
title: Lync 2010 クライアント コンピューターで個人用連絡先ストアを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: 従来のクライアントで使用される個人用連絡先ストアを構成します。'
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833937"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Lync 2010 クライアント コンピューターで個人用連絡先ストアを構成する
  
Skype for Business Server 2015 と Exchange Server 2016 または Exchange Server 2013 を統合している場合は、クライアントが使用する個人用連絡先ストアを構成する必要があります。 特に、Exchange を個人用連絡先ストアとして使用する Skype for Business を構成し、同時に、ユーザーが決定を上書きできないのを確認する必要があります。 これは、各クライアント コンピューターでレジストリ値を作成および構成することで実行できます。
  
> [!NOTE]
> 次の手順は、Lync 2010 クライアント以前を使用するクライアントでのみ必要です。 Lync 2013 クライアントとすべての Skype for Business クライアントには、連絡先ストアの設定を上書きするオプションはありません。
  
ある 1 台のコンピューターでこの値を構成するには、次の手順を実行します。
  
1. クライアント コンピューターで、[スタート] ボタンを **クリックし** 、[ファイル名を指定して実行] を **クリックします**。
2. [ファイル名 **を指定して** 実行] ダイアログ ボックスに「regedit」と入力し、Enter キーを押します。
3. レジストリ エディターで、[ HKEY_LOCAL_MACHINE] を展開し **、[** ソフトウェア] を展開し、[**ポリシー**] を展開し、[ **Microsoft]** を展開して、[ Communicator **。**
4. ユーザー設定を右 **Communicator、[** 新規] をポイントし **、[DWORD (32 ビット) 値] をクリックします**。
5. 新しい値を作成した後、「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。
6. PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディタを閉じます。

複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。 Windows 10 でこれを行う方法について詳しくは、グループ ポリシー オブジェクトの作成に関する記事 [をご覧](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) ください。
  
