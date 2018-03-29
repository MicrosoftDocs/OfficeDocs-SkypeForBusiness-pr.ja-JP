---
title: Skype for Business Server 2015 のクライアント コンピューターでの個人連絡先ストアの構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 と Skype で使用する個人の連絡先ストアを構成します。'
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のクライアント コンピューターでの個人連絡先ストアの構成
 
**の概要:**ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 と Skype で使用する個人の連絡先ストアを構成します。
  
ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 の Skype を統合する場合は、Skype のビジネスを実行している任意のクライアント コンピューターで個人用の連絡先ストアを構成してください。 具体的には、Skype をビジネスで個人の連絡先ストアとして Exchange を使用し、同時に、ユーザーは、その判断をオーバーライドできないことを確認しますを構成する必要があります。 そのためには、各クライアント コンピューターでレジストリ値を作成して構成します。
  
ビジネス用の Skype を実行するコンピューターでこの必要はないことに注意してください。
  
1 台のコンピューターでこの値を構成するには、次の手順を実行します。
  
1. クライアント コンピューターで [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。
    
2. [**ファイル名を指定して実行**] ダイアログ ボックスで「regedit」と入力して、Enter キーを押します。
    
3. レジストリ エディターで、[**HKEY_LOCAL_MACHINE**]、[**Software**]、[**Policies**]、[**Microsoft**]、[**Communicator**] の順に展開します。
    
4. [**Communicator**] を右クリックし、[**新規**] をポイントし、[**DWORD (32 ビット) 値**] をクリックします。
    
5. 新しい値を作成すると後、は、PersonalContactStoreOverride を入力し、enter キーを押して値の名前を変更します。
    
6. PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディターを閉じます。
    
複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。 詳細については、グループ ポリシーのマニュアルを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543)。
  

