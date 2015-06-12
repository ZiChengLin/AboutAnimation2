# AboutAnimation2
、CALayer渲染

//
//  ViewController.m
//  Lesson-UI0612-2
//
//  Created by 林梓成 on 15/6/12.
//  Copyright (c) 2015年 lin. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view, typically from a nib.
    
    UIButton *button = [UIButton buttonWithType:UIButtonTypeCustom];
    button.frame = CGRectMake(40, 135, 135, 135);
    [button setImage:[UIImage imageNamed:@"1.png"] forState:UIControlStateNormal];
    [self.view addSubview:button];
    
    // 使用UIView的属性layer做视图的改变
    // 为一个view或子类设置一个边框即颜色
    [button.layer setBorderWidth:2];
    [button.layer setBorderColor:[UIColor orangeColor].CGColor];
    // 设置弧度的半径
    [button.layer setCornerRadius:67.5];
    // 切掉边框以外的视图（只是切除了layer层）
    //[button.layer setMasksToBounds:YES];
    
    // 设置图层的阴影、偏移量和透明度 (默认透明度是全透明的)
    [button.layer setShadowColor:[UIColor redColor].CGColor];
    [button.layer setShadowOffset:CGSizeMake(15, 15)];
    [button.layer setShadowOpacity:0.5];
    // 设置阴影的弧度
    [button.layer setShadowRadius:20];
    
    
#pragma mark CALayer
    CALayer *layer = [CALayer layer];
    layer.frame = CGRectMake(120, 300, 135, 135);
    [self.view.layer addSublayer:layer];            // 设置到self.view.layer层上
    // 往layer层上面添加需要渲染的东西
    layer.contents = (id)[[UIImage imageNamed:@"1"] CGImage];
    layer.borderWidth = 2;
    layer.borderColor = [UIColor greenColor].CGColor;
    
    
}

- (void)didReceiveMemoryWarning {
    [super didReceiveMemoryWarning];
    // Dispose of any resources that can be recreated.
}

@end



