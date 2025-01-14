# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# General polynomial estimator of the regression discontinuity Use rdd_gen_reg With (In) R Software
install.packages("rddtools")
library("rddtools")
rdd_gen_reg = read.csv("https://raw.githubusercontent.com/timbulwidodostp/rdd_gen_reg/main/rdd_gen_reg/rdd_gen_reg.csv",sep = ";")
# Estimation General polynomial estimator of the regression discontinuity Use rdd_gen_reg With (In) R Software
rdd_gen_reg_rdd <- rdd_data(y=rdd_gen_reg$y, x=rdd_gen_reg$x, cutpoint=0)
rdd_gen_reg_rdd$y <- with(rdd_gen_reg_rdd, ifelse(y<quantile(y, 0.25), 0,1))
rdd_gen_reg_rdd <- rdd_gen_reg(rdd_object=rdd_gen_reg_rdd, fun= glm, family=binomial(link='probit'))
print(rdd_gen_reg_rdd)
summary(rdd_gen_reg_rdd)
# General polynomial estimator of the regression discontinuity Use rdd_gen_reg With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished