# Sequelize

## 同じカラムに複数のLIKEをAND条件で使用する
- https://github.com/sequelize/sequelize/issues/9195 

## 条件句のサンプル

```js
Repository.findAll({
  where: {
    id: 1,
    name: {
      [Sequelize.Op.like]: '%foo%',
    },
  },
  order {
    
  },
  limit: 10,
});
```